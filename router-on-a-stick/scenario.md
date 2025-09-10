# Scenario

Up to now, we have used the same scenario for all our exercises. I do not want to make the configurations any more complex, so I am going to only implement a subset of functionality in the next exercises. The size of our switched network is irrelevant to the next tasks we have to do.

Our earlier exercises did not assume we would have multiple sites with multiple VLANs. If this will be the case, I will always use a more scalable IPv4 address mapping.

Every site will use the third octet as a differentiator.&#x20;

My main site, HQ will be site 1. Its IP address range will use 10.1.x.x

The second site will be site 2. Its IP address range will use 10.2.x.x&#x20;

I will use the same VLAN map for each site. VLANs are layer 2, once we start routing, VLAN information does not pass. VLAN 2 on site 1 is a completely different Ethernet to VLAN2 on site 2.

My VLAN table for site 1 will be

| **VLAN** | **Purpose**          | **IPv4**  | **Subnet** |
| -------- | -------------------- | --------- | ---------- |
| 1        | ISP                  | 10.1.1.0  | /24        |
| 2        | Hosts                | 10.1.2.0  | /24        |
| 3        | Staff Radio          | 10.1.3.0  | /24        |
| 4        | Power Infrastructure | 10.1.4.0  | /24        |
| 5        | Clients              | 10.1.5.0  | /24        |
| 6        | Servers              | 10.1.6.0  | /24        |
| 7        | Telephony            | 10.1.7.0  | /24        |
| 8        | HVAC Infrastructure  | 10.1.8.0  | /24        |
| 9        | Storage              | 10.1.9.0  | /24        |
| 10       | NetMan               | 10.1.10.0 | /24        |
| 11       | Security Cameras     | 10.1.11.0 | /24        |
| 12       | OOBM                 | 10.1.12.0 | /24        |
| 13       | ClusterChat          | 10.1.13.0 | /24        |
| 14       | Loopbacks            | 10.1.14.0 | /24        |
| 15       | Routers              | 10.1.15.0 | /24        |
| 16       | Links                | 10.1.16.0 | /24        |

Our switches on each network (Y) will be 10.Y.10.21

Our VPC is 10.Y.X.101 and it may move VLANs, we will reserve 101 on each VLAN for it.

Our Automation Container has a reserved address 10.Y.X.101
