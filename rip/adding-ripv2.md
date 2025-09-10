# Adding RIPv2

Check the routing tables in each router. Each router only knows about the routes that are directly connected.

Setting up RIP is easy; we switch it on and then tell the router which networks to advertise.&#x20;

```
hostname Router1

router rip
 version 2
 no auto-summary
 network 192.168.1.0
 network 192.168.101.0
 network 192.168.102.0
 network 192.168.103.0
 exit
```

<pre><code><strong>hostname Router2
</strong>
router rip
 version 2
 no auto-summary
 network 192.168.2.0
 network 192.168.101.0
 network 192.168.104.0
 network 192.168.105.0
 exit
</code></pre>

```
hostname Router3

router rip
 version 2
 no auto-summary
 network 192.168.3.0
 network 192.168.106.0
 network 192.168.102.0
 network 192.168.105.0
 exit
```

```
hostname Router4

router rip
 version 2
 no auto-summary
 network 192.168.4.0
 network 192.168.106.0
 network 192.168.104.0
 network 192.168.103.0
 exit
```

Type the command **sh ip route** on each router. Each router should now have a route to every LAN network and you should be able to see which network we missed including! My example is from Router1.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

I can see the other 3 LANs and I see them via their own router gateways.

Do ping tests from VPCS1 to each VPCS to ensure connectivity.
