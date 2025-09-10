# Build

For the exercise in this session, write your commands in Notepad++ and copy & paste into the terminal. Once configurations get complex, writing at the terminal is inefficient.

1\.      Open a new network in GNS3 called save as **SimpleOSPF**

2\.      I have configured the hardware as shown. The switches are simple, unmanaged switches.

The diagram below meets most of the requirements for a physical network diagram.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

One thing I can assure you of; if you cannot draw the network, you are not ready to start configuring it. Pre-requisites for network design are large sheets of paper, coloured markers, and much coffee! The diagram below meets most of the requirements for a logical network diagram.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Build the network and do a ping test to make sure you have some connectivity. After having previously implemented static routes and RIP, you should know what pings will work and what should not!&#x20;

If in doubt, try the command **show ip route**, if your router does not know about a subnet, it will not be able to reach it.
