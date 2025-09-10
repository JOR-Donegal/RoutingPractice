# Configure Routing

On a physical router, we have physical interfaces and would configure these to each be on different subnets. By default, every port on a switch is a switch port, it is implicit and does not show in the interface configurations. To change this port to be a router port, we could use the command&#x20;

```
no switchport
```

on the interface. We will not use that for now.

When we use a switch for campus routing, we use _switch virtual interfaces_ (SVI). These appear in almost every way exactly like a router interface. For this to work, the VLAN should be preconfigured, active, and at least one access port should be configured in this VLAN.

We may already have two virtual interfaces on our switches. We initially had an IP address in VLAN 1, and we added a management address in VLAN 10. Although we have two interfaces, we do not have routing functionality, these interfaces can be used for management access only. All our switches are layer two only. To make them layer three, we need to add a line to the configuration.

```
ip routing
```

If you get an error when you try to do this, your switch does not support L3. Check the image you are using, or the model of real hardware.

Go to Switch21, do a&#x20;

```
show vlan
```

to ensure you have all the VLANs as per the scenario.

Add SVIs and IPv4 addresses for all the VLANs, use a script, and keep it for later. I show my script for the fist few VLANs. Make sure you know the difference between creating a VLAN and creating an interface into a VLAN. They are two completely different things, but many students miss the significance.

```
en
conf t

ip routing

int vlan 2
 description "Hosts Router"
 ip address 192.168.2.21 255.255.255.0
 no shut
 exit

int vlan 3
 description "Radio Router"
 ip address 192.168.3.21 255.255.255.0
 no shut
 exit

int vlan 4
 description "PowerLAN Router"
 ip address 192.168.4.21 255.255.255.0
 no shut
 exit

int vlan 5
 description "Cients Router"
 ip address 192.168.5.21 255.255.255.0
 no shut
 exit
 
int vlan 6
 description "Servers Router"
 ip address 192.168.2.21 255.255.255.0
 no shut
 exit
```

Change your script and do the same configuration on Switch22 and 23. Remember to change the last octet of each interface!

For testing, I want my PCs on the Client LAN and I need to give them appropriate addresses. For each subnet, keep:

* &#x20;0 is reserved as a network address
* 1-3 for routers
* 4-99 reserved for fixed use
* 101-199 for DHCP
* 200-254 reserved for static assignment
* 255 is reserved as a broadcast address

## PC1

I will give PC1 the address 192.168.5.201/24 and give it an appropriate gateway on VLAN5.&#x20;

```
ip 192.168.5.201 255.255.255.0 192.168.5.21
```

It is connected to Switch22, gi0/1. I now move that to VLAN5.

```
conf t
int gi0/1
 switchport access vlan 5
 exit
```

Do a test ping to each interface on VLAN5 (21, 22, 23).

Do a test ping to each interface on VLAN6 (21, 22, 23) to confirm routing is working.

## PC2

Give PC2 the address 192.168.5.202 and set gi0/1 on Switch23 to VLAN5.

Repeat all the same tests from PC2. A methodical approach might be:

* Ping the gateway on the network you are on
* Ping another host on the network you are on
* Ping an address on all the other networks to see if routing works and has been configured correctly
