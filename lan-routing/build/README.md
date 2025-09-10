# Build

In GNS3, I opened the previous _Scripting_ project and saved it as _InterVLAN_.

Although we have covered the basics of IPv4 routing in lectures, you will probably have to do some additional reading/research as we go along to understand commands and terminology.

As you will be aware, IPv4 networks were originally based on _classful routing_. This was wasteful of address space and is one of the reasons why the world ran out of addresses. Suppose I break up 10.0.0.0/8 into class C subnets, I have an interface to 10.0.1.0/24 and 10.0.2.0/24 and I have a default route. If I try to reach the IP address 10.0.3.123 the packet will be dropped as destination unreachable. Because the router has a route to 10.0.0.0/8 but has no entry for 10.0.32.0/24, it sees the whole subnet as being unreachable.

There is a subtle difference in the behaviour of routers which perform classless routing. In this case, where no path to 10.0.3.0/24 exists, the router will use the default route.

It seems a subtle difference, but if your routers are configured to be in classful mode, you need to switch that off before you begin configuring. Most modern equipment defaults to classless.

To get packets off a network at layer 3, we need a gateway address. Whenever a PC is trying to access a node which is not on the same subnet as it, it will forward the packet to the gateway. We can have more complex arrangements where PCs have routing tables and can make choices amongst multiple gateways. In practice this is sometimes done with servers but is a bit unusual.

When designing enterprise networks with multiple routers, it is common practice to give each router a number (e.g. Router21, Router22) and to use this number as the last octet in the router’s IP address on each subnet it participates on.

For example, if we have three VLANs and subnets, and we are using Switch1 as our router. Look at the table below, see if it makes sense.

<table><thead><tr><th width="175">Router Device</th><th width="187">NetMan</th><th width="186">Hosts</th><th>Radio</th></tr></thead><tbody><tr><td>Switch21</td><td>192.168.10.21</td><td>192.168.2.21</td><td>192.168.3.21</td></tr></tbody></table>

We know that whatever subnet we are on, we will be using .21 as the gateway. Handy that!

On larger networks, we tend to number our routers like this (Router1, 2, 3, 4, 5 in the case of ATU Letterkenny). We will use a neat trick to share a gateway address amongst the routers for redundancy. For example, in ATU Letterkenny whichever router is active pretends it is .20 on the subnet it is on. If that router fails, another one pretends it is .20 and so on. The technology to do this is called _Virtual Router Redundancy Protocol_ (VRRP). Cisco has a proprietary implementation called _Hot Standby Router Protocol_ (HSRP).&#x20;

We will look at this in a later session.
