# Wiring up

On each switch, we had configured gi0/1 in the NetMan VLAN. Verify this is the case on Switch21.

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Connect the Network Automation container to this port.

Right-click the Network Automation device and **Configure**. Then click to **Edit** the network configuration.

<figure><img src="../.gitbook/assets/2.jpg" alt=""><figcaption></figcaption></figure>

I edit and uncomment so my Network Automation device is 192.168.10.103.

<figure><img src="../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

I Save and Apply. Then I stop and start the Network Automation device. Then I verify if I have the correct address.

<figure><img src="../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

Finally, do a ping test to the other network devices.
