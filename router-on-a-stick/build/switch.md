# Switch

I create a single switch as **Switch21** with the following configuration. Note that the only SVI is for switch management, this will not be a router!

```
en
conf t

hostname Switch21

# Configure VLANs
vlan 2
 name Hosts
 exit
vlan 3
 name StaffRadio
 exit
vlan 4
 name Power
 exit
vlan 5
 name Clients
 exit
vlan 6
 name Servers
 exit
vlan 10
 name NetMan
 exit
vlan 14
 name Loopbacks
 exit
vlan 15
 name Routers
 exit
vlan 999
 name Native
 exit
vlan 1000
 name Discard
 exit

# Configure ports
Interface range GigabitEthernet0/0-3
 description Clients
 switchport access vlan 10
 switchport mode access
 negotiation auto
 exit
 
Interface range GigabitEthernet1/0-3
 description Servers
 switchport access vlan 6
 switchport mode access
 negotiation auto
 exit 

Interface range GigabitEthernet2/0-3
 description Unused
 switchport access vlan 1000
 switchport mode access
 negotiation auto
 shutdown
 exit
 
Interface range GigabitEthernet3/0-3
 switchport trunk encapsulation dot1q
 switchport trunk native vlan 999
 switchport mode trunk
 negotiation auto
 exit

# Configure SVI for management only
interface Vlan10
 description "interface to NetMan"
 ip address 10.1.10.21 255.255.255.0
 no shut
 exit

exit
wr mem
```

I also configured PC1 as

```
ip 10.1.10.101 255.255.255.0 10.1.10.1
```

Finally, a ping test between PC1 and 10.1.10.21 verifies VLAN 10. Note that .21 is no longer a gateway, its just the management address of the switch on VLAN 10. We will configure a router at .1 in the next step.
