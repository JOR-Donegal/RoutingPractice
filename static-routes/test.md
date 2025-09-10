# Test

I did a ping test

* Between Routers, these should all work fine.
* From each VPCS to its gateway, these should all work fine.
* From each VPCS to the WAN interface (gi0/0) on its own router, these should all work fine.
* If I try to ping the WAN interface of the other router, no response. The same is true of the LAN interface on the other router, and the other VPCS.

Verify these tests on your system.

If you try the command **sh ip route** at each router you should be able to figure out why this is the case.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Router1 knows about network 192.168.1.0/24 and 192.168.3.0/24 and can communicate with them.

Router2 knows about network 192.168.2.0/24 and 192.168.3.0/24 and can communicate with them.

The routers know about these networks because they are directly connected. No other communication is possible!
