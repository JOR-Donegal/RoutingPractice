# Build

I create the network as shown and save as **StaticRoutes**, using generic switches and Cisco IOSv routers.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

I configure VPCS1

```
ip 192.168.1.101/24 gateway 192.168.1.1
```

And VPCS2

```
ip 192.168.2.101/24 gateway 192.168.2.2
```

I configured the routers as shown. We all have methodologies we have developed over the years in the field. Routers have many interfaces in different LANs. I always keep the last octet the same as the router number. For example, Router1 will be x.x.x.1 in every subnet to which it is connected.&#x20;

I have two LANs, 192.168.1.0/24 and 192.168.2.0/24. I have configured a single WAN connection (192.168.3.0/24)

```
hostname Router1

int gi0/1
 ip address 192.168.1.1 255.255.255.0
 no shut
 exit
int gi0/0
 ip address 192.168.3.1 255.255.255.0
 no shut
 exit
exit
```

```
hostname Router2

int gi0/1
 ip address 192.168.2.2 255.255.255.0
 no shut
 exit
int gi0/0
 ip address 192.168.3.2 255.255.255.0
 no shut
 exit
exit
```
