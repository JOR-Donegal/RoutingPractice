# Test a script

In the console for the Network Automation device, type&#x20;

```
Python3 
```

and verify what version you are running. You can run any Python code here.

The simplest example every scripter starts with is to connect to a switch with Telnet. Read the [Python example](https://docs.python.org/3/library/telnetlib.html) first. I previously discovered what steps I needed to follow to login, go to elevated privilege and exit.

I copy the sample code and edit it as shown below.

```
import telnetlib

HOST = "192.168.10.21"
password = "JOR"

# Connect
tn = telnetlib.Telnet(HOST)

# Find the password prompt and respond
tn.read_until(b"Password: ")
tn.write(password.encode('ascii') + b"\n")

# Enable 
tn.write(b"enable\n")

# Exit gracefully
tn.write(b"exit\n")

# Print out what we got
print(tn.read_all().decode('ascii'))
```

In the console for the Network Automation device, type&#x20;

```
nano telnet1.py
```

I paste the sample code into this nano session then \[ctrl o] to save, \[ctrl x] to exit. When I test, I verify that I connected and got privilege elevation.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Simple test, but you can build on this.
