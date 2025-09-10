# Build

In GNS3, I opened the previous _RouterOnAStick_ project and saved it as _Internet_

Before I can proceed, I need to map the connectivity in my own computer. I prefer to use a bridged network for GNS3, but you will not have that option in ATU laboratories. I'm going to demonstrate using the NAT'd network.

My UB2204 instance has an IP address of 192.168.146.157.

My host instance has an IP address of 192.168.146.1 but also has a physical adapter 192.168.5.21 on my home network. If you cannot draw it, you are not ready to work on it!

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

My starting point: the Ubuntu instance can see the Internet via eth0.
