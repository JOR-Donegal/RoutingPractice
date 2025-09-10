# Router

I add a router as **Router1** and connect it to **Switch21** as shown. Remember, all my port in range Gi3/0-3 are trunk/tagged ports.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Gi0/0 on the router now needs to be configured to send out tagged packets. We do this by defining sub-interfaces. For example, for VLAN 10 I configure the switch as follows.

```
en
conf t

hostname Router1

# Enable the physical interface
int gi0/0
 no shut
 exit

# Set up VLANs
int gi0/0.10
 encapsulation dot1Q 10 
 ip address 10.1.10.1 255.255.255.0
 no shut
 exit

```

If you have done everything correctly, a ping test from PC1 to 10.1.10.1 works.

I also create a subinterface for VLAN5

```
int gi0/0.5
 encapsulation dot1Q 5
 ip address 10.1.5.1 255.255.255.0
 no shut
 exit
```

If you have done everything correctly, a ping test from PC1 to 10.1.5.1 works and you have routing.

## Exercise

1. Create and test a sub-interface for VLAN 6.
2. Configure Switch21, Port Gi0/1 in VLAN5
3. Connect a test PC to Switch21, Port Gi0/1 (PC2), IP address 10.1.5.102
4. Do ping tests from PC2 to all the other nodes.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
