# Static Routes

The format of the command to create a static route is&#x20;

ip route <mark style="color:blue;">Destination\_Network</mark> <mark style="color:red;">Destination\_Subnet</mark> <mark style="color:orange;">Next\_Hop</mark>

For example, on Router1 we need to tell it we can find 192.168.2.0/24 via 192.168.3.2

```
ip route 192.168.2.0 255.255.255.0 192.168.3.2
```

On Router2 we need to tell it we can find 192.168.1.0/24 via 192.168.3.1

```
ip route 192.168.1.0 255.255.255.0 192.168.3.1
```

You should now be able to ping one PC from the other, although the first two pings may timeout (why?).&#x20;

Run the **show ip route** command again. Can you see how the static route is represented?

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

This is a handy, simple, and fool-proof technique for indicating routes. Can you think of any downside to static routes, in a network with frequent moves and changes?

Would this technique scale well to an SME with 4 sites; or 40?
