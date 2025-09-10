# Breaking the WAN

We are going to attack the path between VPCS1 and VPCS4 next.

On Router1, do a traceroute to VPCS4.

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

The packet goes by the most direct route.

Now delete the link between Router1 and Router4.

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

I need to wait a minute for the network to reconverge.&#x20;

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

It looks like there are multiple paths! But the ping gets through.

I delete one more link, from Router2 to Router4.

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

I still have a path!

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

One final piece of vandalism!

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

There is still a path, albeit with four hops.

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

Despite having broken half the links on our WAN, we still have fully functional connectivity. If ANY route exists between two points, RIP will use that information to provide a route for packets. There are some limitations, RIP only allows for a certain number of hops (how many?).&#x20;

Other limitations with RIP are dealt with in my theory notes.
