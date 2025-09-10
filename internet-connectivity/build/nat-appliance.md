# NAT Appliance

I drag and drop a NAT appliance into my project and connect it to Router1, Gi0/1.

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

I need to tell my router to get its IP address via DHCP from the NAT. I configure Gi0/1 as follows.

```
int gi0/1
 ip address dhcp
 no shut
 exit
```

I test it works by pinging an external IP address (like 8.8.8.8). Interestingly, when I assign an IP address using DHCP, the router assumes I'm connecting to the Internet and creates a default route on that interface. Try the command

```
sh ip route
```

This will indicate a default route to 0.0.0.0/0

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

Add the following lines to Router1 so we can do a DNS lookup.

```
ip domain-lookup
ip name-server 8.8.8.8
```

I can now ping www.google.ie and confirm that ping and DNS both work.

Now go and try to ping from PC1.&#x20;

You can get through the network fine, but you will not be able to ping an Internet address!
