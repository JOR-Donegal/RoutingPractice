# Configure the switches

We need an account we can use for remote login. At each switch, add the following configuration, using your own initials.

```
user JOR password JOR
enable password JOR
```

We also need to set a password on the remote login.

```
conf t
line vty 0 4
password JOR
```

Save these configuration changes.

In the console for the Network Automation device, type

```
telenet 192.168.10.21
```

## Test

You should be able to login using the password you just set. If not go back and retrace your steps.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Note the prompt is "Password". You will need to know this later!

If I want to get to privileged mode, I get another password prompt which I must respond to.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Working!
