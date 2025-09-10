# Passive Interfaces

Having OSPF packet egressing on LANs with clients is a waste of bandwidth at best and a security problem certainly. Passive interfaces

The command **passive-interface gi0/0** causes that interface to become passive.

The command **passive-interface default** causes all the interfaces to become passive.

The command **no passive-interface gi0/0** enables the protocol on that interface only.

There are two router interfaces into client subnets.

Router10 - Gi0/1&#x20;

Router11 - Gi0/2

On Router10

```
router ospf 1
 passive-interface gi0/1
```

On Router11

```
router ospf 1
 Passive-interface gi0/2
```

This time, if you see any error message, you picked the wrong interface!!
