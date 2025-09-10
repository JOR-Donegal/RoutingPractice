# Setting Priorities

We do not like uncertainty in our network design, I will set priority on each of the switches.

* Switch23                180
* Switch22                190
* Switch21                200

I type these commands on Switch21

```
en
conf t
int vlan 5
 standby 1 priority 200
 exit
exit
```

Even after I make this change, the&#x20;

```
show standby
```

command indicates that Switch23 is still active. It is considered less disruptive, and this priority will not be enforced until Switch23 goes down.

We will be resetting switches, so save your configurations on each switch with the command&#x20;

```
wr mem
```

Restart Switch23

Go to switch 21 and type&#x20;

```
show standby
```

What has changed and why?
