# WAN Design

When building networks, we may start with a star topology and then create a ring, so every site has three connections to the WAN. Sometimes we say we put the spokes on the bicycle wheel and then add the rim!

Some questions…

* How many serial connections does each router need to connect to every other router?
* How many static routes would we need to define?
* Can you think of a formula which would describe this growth as the number of fully meshed routers increases?
* If we lose a connection from one router to another, can the system maintain connectivity?

For the number of links in a full mesh network, use the formula:

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Where N is the number of nodes. In our case, this becomes:

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

Every router would need a static route to every local LAN and to every WAN subnet to which it was not directly connected. It would be difficult to maintain this network if we used static routes.

We are going to use a dynamic routing protocol instead.

Probably the simplest protocol we could use would be RIPv2. This has been previously covered.
