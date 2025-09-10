# Link Costs

Next check the routing table on Router10.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Note that the routing table is giving us the administrative distance and the cost of each route. The cost is 2 either way (due to the 100MB/s switches, each route appears to be 2 x 100MB/s hops) so OSPF indicates both routes and will attempt to load balance.

If I change the cost of one route on Router10:

```
interface GigabitEthernet0/0
 ip address 192.168.238.10 255.255.255.0
 ip ospf cost 10
 duplex auto
 speed auto
```

Then the less favoured route will no longer show in the routing table on Router10.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

I must look into the interface to see what the OSPF cost and status is.

```
sh ip ospf int gi0/0
```

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
