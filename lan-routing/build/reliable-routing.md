# Reliable Routing

In the previous exercise we configured simple static routing and did some basic tests. Our scenario is for a campus site with three separate buildings. At layer 2, we built the network as a ring so that if any single switch or link fails, everything else still works.&#x20;

However, from a routing perspective, failure of a switch/router may disable routing. We never configure networks with single point of failure! In this exercise, we will look at a typical configuration for reliable routing. On completion, each of the buildings should be able to work in isolation, and routing will still function if any single switch is powered up and working.

The general thing we are trying to configure is referred to as gateway redundancy. This is a standard configuration in just about every enterprise and data centre network. Consider the diagram below, a logical diagram of what we want to achieve to make VLAN5 redundant.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

VLAN 5 uses a single gateway address with the last octet of .20 even though there is no router 20. Each of the actual routers (21, 22, 23) can pretend it is .20 and provide routing services to the subnet. If that router fails, another router will take over.

The main campus in ATU Letterkenny works the same way. Each subnet has a real physical router (1,2,3) which shares the IP address .20 as the gateway.

There are three common protocols which can be used for this functionality.

* Hot Standby Routing Protocol (HSRP)
* Virtual Router Redundancy Protocol (VRRP)
* Gateway Load Balancing Protocol (GLBP)

HSRP is a proprietary Cisco protocol so will avoid it unless we have a network which uses only Cisco equipment. However, it is the easiest to demonstrate in this walk-through uses it.

VRRP is a standards-based protocol using RFC5798 for version 3 from 2010, and the configuration is very similar. One nice option is that you can define two separate VRRP addresses per VLAN and do load balancing. There are subtle differences, feel free to do some reading!

GLBP implements load balancing without separate redundancy groups. There are a few algorithms for this, round robin, host dependent, and weighted. This protocol is Cisco proprietary, and I have honestly never seen it used on a real site.
