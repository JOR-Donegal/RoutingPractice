# NAT at the Router

The NAT device is very simple, it will translate whatever is on its internal subnet to the external interface of UB2204, or whatever you are running GNS3 on.&#x20;

The NAT device is on the subnet 192.168.122.0/24, it has no idea how to get back to PC1 on 10.1.10.0/24.

We must NAT at the router!

```
ip nat inside source list 1 int gi0/1 overload
access-list 1 permit any
int gi0/1
 ip nat outside
int gi0/0.5
 ip nat inside
```

My PC2 is on VLAN 5, if I test, I can now ping 8.8.8.8

My PC1 is on VLAN 10, it still cannot ping out. I add a NAT for that as well.

```
int gi0/0.10
 ip nat inside
```

The ping to 8.8.8.8 works!
