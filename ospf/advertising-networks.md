# Advertising Networks

In previous sessions (e.g. RIP) you have seen the network command. In OSPF we use the network command, but we also tell OSPF the size of each network. Instead of using subnet masks we use wildcard masks or inverse subnet masks. These should be covered in lectures. In a normal subnet mask, the bits are 1 for the subnet part of the address and 0 for the node part of the address. In OSPF we are indicating which part of the address is a wildcard (wildcard means “can be anything”) by using 1. For example, a class C network will be identified as 0.0.0.255 which means we need to match the first 24 bits of the address and the last 8 bits are a wildcard.

As another example, a /30 network has four IP addresses of which 2 are usable; the last two bits show node number and the first 30 bits show network number. The subnet mask for this is 255.255.255.252 or in binary 1111 1111 1111 1111 1111 1111 1111 1100. The inverse subnet mask is 0.0.0.3 or in binary 0000 0000 0000 0000 0000 0000 0000 0011.

Some other examples are shown below.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The inverse mask is not intuitive to me, even after all these years!
