# Initial Configuration

I configured the two routers as shown. I will configure the perimeter router (Router2) later.

```
conf t
hostname Router10
enable secret Passw0rd

interface Loopback1
 ip address 192.168.255.10 255.255.255.255

interface GigabitEthernet0/0
 ip address 192.168.238.10  255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit
 
interface GigabitEthernet0/1
 ip address 192.168.1.10 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit
 
interface GigabitEthernet0/2
 ip address 192.168.2.10 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit

router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 192.168.2.0 0.0.0.255 area 0
 network 192.168.238.0 0.0.0.255 area 0
 exit
exit
wr mem

```

```
conf t
hostname Router11
enable secret Passw0rd

interface Loopback1
 ip address 192.168.255.11 255.255.255.255

interface GigabitEthernet0/0
 ip address 192.168.238.11 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit
 
interface GigabitEthernet0/1
 ip address 192.168.2.11 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit
 
interface GigabitEthernet0/2
 ip address 192.168.3.11 255.255.255.0
 duplex auto
 speed auto
 no shutdown
exit

router ospf 1
 network 192.168.3.0 0.0.0.255 area 0
 network 192.168.2.0 0.0.0.255 area 0
 network 192.168.238.0 0.0.0.255 area 0
 exit
exit
wr mem
```

The router will immediately identify that they have become neighbours and indicate on which interfaces. For example, on Router11;

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

To verify try the command **show ip ospf neighbor** and check the output. On Router10;

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

I can see Router11 via two different routes. If at any stage you need to restart the OSPF process, try the command **clear ip ospf process**

The command **show ip protocols** will show the overall status of routing protocols and the router ID. On Router11:

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

There is a lot of useful information here, run through and make sure you understand it all!
