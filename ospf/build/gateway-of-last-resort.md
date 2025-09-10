# Gateway of Last Resort

I have connected the Cloud to Router2, gi0/1 and configured it as shown.

```
conf t
hostname Router2

int gi0/1
 ip address DHCP
 no shut

interface Loopback1
 ip address 192.168.255.2 255.255.255.255

interface GigabitEthernet0/0
 ip address 192.168.238.2 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit

router ospf 1
 default-information originate always
 network 192.168.238.0 0.0.0.255 area 0
 exit

exit
wr mem
```

Both Router10 and 11 should show Router2 coming up and Router2 should also give a message confirming an adjacency to Routers 10 and 11. My routing tables on Router10 and 11 should show my default route.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Finally we need to add NAT to Router2 so the whole network can see outbound.

```
ip nat inside source list 1 int gi0/1 overload
access-list 1 permit any
int gi0/1
 ip nat outside
int gi0/0
 ip nat inside
```

From Router10, I can now ping to my physical home network (my test address is 192.168.5.10, what should yours be?).

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>
