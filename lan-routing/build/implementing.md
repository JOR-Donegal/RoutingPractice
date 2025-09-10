# Implementing

For each of our subnets we have switches 21, 22 and 23 and each can act like a router. Make sure all switches are configured as routers. You should know how to do all of this!

We will use .20 as a gateway address on each subnet and for now we will only set up redundancy on VLAN 5. We can do this with one command per switch.

```
en
conf t
int vlan 5
 standby 1 ip 192.168.5.20
 exit
exit
```

On each of your test PCs, change the gateway address to .20 and re-verify connectivity.

I ping all four possible gateways from PC1 and then check the ARP table.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

As you can see the physical gateways and fail-over gateway (192.168.5.20) have different MAC addresses. HSRP uses the MAC address 00:00:0C:07:AC:_xx_ where _xx_ is the HSRP group number, in our case 1.

If we were using VRRP, the MAC address would be 00:00:5E:00:01:_xx_

On any switch, I type the command

```
show standby
```

I get the following result.

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

The active router is local (21) and 23 is a standby. Check this on each switch, they should agree.

We can see which router is acting as active and standby. The switch with the highest priority will become active in the switch with the next priority will become standby. We did not set a priority value, so the tiebreaker is the IP address. For this reason, Switch23 is active.
