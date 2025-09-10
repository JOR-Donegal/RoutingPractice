# Authentication

Before we go live, we should always configure authentication. This is good prevention for inadvertent insertion of routes but is not really secure. From IOS 15.4 Cisco includes more modern cryptography.

The following interfaces connect to other routers.

Router2 - Gi0/0&#x20;

Router10 - Gi0/0, Gi0/2&#x20;

Router11 - Gi0/0, Gi0/1

Add the following code on Router2

```
interface GigabitEthernet0/0
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 MyMD5
 exit
```

Add the following code on Router10.

```
interface GigabitEthernet0/0
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 MyMD5
 exit
  
interface GigabitEthernet0/2
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 MyMD5
 exit
exit
```

Add the following code on Router11

```
interface GigabitEthernet0/0
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 MyMD5
 exit

interface GigabitEthernet0/1
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 MyMD5
 exit
```

We do not need to do this on the interfaces which do not go to another router. As you are doing this, routing will fail as you change one router at a time.

We can check on any interface to see that crypto is enabled.

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>
