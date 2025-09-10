# Timers

Run the command **show ip ospf interface gi0/0** and record the output. I am using Router2. The timers are visible in the middle of the output.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-21 171433.jpg" alt=""><figcaption></figcaption></figure>

We can tune these, but we must do it the same on both side of a link (or on all routers on a broadcast subnet). There are two router connections into subnet 192.168.2.0/24:

Router10 - Gi0/2&#x20;

Router11 - Gi0/1

I will now change both.

On Router10

```
int gi0/2
 ip ospf hello-interval 5
 ip ospf dead-interval 20
 exit
exit
```

On Router11

```
int gi0/1
 ip ospf hello-interval 5
 ip ospf dead-interval 20
 exit
exit
```

If you do one at a time, you will notice the neighbour down message.
