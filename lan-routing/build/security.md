# Security

One of the oldest (and most common!) attacks involves crafting packets so they appear to have someone else’s IP address; this is called IP spoofing. Various protections mechanisms exist but for now, examine Unicast Reverse Path Forwarding (RPF). It might help to read the IETF best practices BCP38 and BCP84.

As with everything, there are implications. Turning on URPF on some devices requires two lookups in the hardware path, cutting the size of the hardware’s most expensive resources (like the TCAM) in half!!

There is an authentication option in the **standby** command on each interface, this should be used on any real deployment.
