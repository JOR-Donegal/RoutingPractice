# Testing

You need to demonstrate you understand the basic commands given for testing here and the significance of the information you are getting back.

Test each point-to-point link with a ping and verify connectivity.

One router at a time, check that you can see all neighbouring routers. For example, on Router1 I get

```
%BGP-5-ADJCHANGE: neighbor 192.168.12.2 Up
%BGP-5-ADJCHANGE: neighbor 192.168.14.4 Up
%BGP-5-ADJCHANGE: neighbor 192.168.13.3 Up
```

The command&#x20;

```
show ip bgp summary 
```

gives confirmation of most information we need to see if BGP is working.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Now verify the detailed configuration of each connection using the&#x20;

```
show ip bgp neighbour
```

command. The output listing will be long and will take some time to go through, do so lightly!

The command

```
show ip bgp 
```

is useful, as it gives the contents of the BGP table. Spend a little time on this, in particular, understand the information you are getting in the path column.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

The command

```
show ip protocols 
```

gives me some very useful summary information, including the administrative distances for internal and external BGP.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

In the end, we need to see what ended up in the routing table.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>
