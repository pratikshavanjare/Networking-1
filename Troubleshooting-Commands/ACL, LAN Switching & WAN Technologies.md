# ACL, LAN Switching & WAN Technologies

## 1. ACL (Access Control List)

ACLs are like security guards for your router.
They decide who is allowed and who is blocked from entering or leaving the network.

**What ACLs do:**

- Allow or deny traffic
- Filter based on IP, port, or protocol
- Protect networks from unwanted access

**Simple Examples:**

Allow only one IP:
```
access-list 10 permit 192.168.1.10
```

Deny a network:
```
access-list 20 deny 10.0.0.0 0.0.0.255
```

Apply ACL to an interface:
```
interface g0/0
 ip access-group 10 in
```

----------------------

## 2. LAN Switching

LAN switching is how switches move data inside a local network (like your office).
Switches use MAC addresses to forward frames to the right device.

**Key features:**

- Reduces collision
- Increases speed
- Supports VLANs
- Makes communication inside LAN efficient

**Useful Commands:**

**See MAC table:**
```
show mac address-table
```

**Create Vlan**
```
vlan 10
 name SALES
```

**Assign port to VLAN:**
```
interface fa0/1
 switchport access vlan 10
```

--------------------------------------

## WAN Technologies - MPLS, Leased Lines, VPN, Broadband(4G/5G) WAN

WAN connects different locations—like connecting two offices in different cities.
Unlike LAN, WAN uses telecom networks, ISPs, and long-distance links.

**Common WAN Types:**

- **MPLS** – fast, reliable, widely used
- **Leased Line** – dedicated private link
- **VPN** – secure connection over internet
- **4G/5G WAN** – wireless backup links

**Useful Troubleshooting Commands:**

**Check interface status:**
```
show ip interface brief
```

**Check routes:**
```
show ip route
```

**Check WAN encapsulation:**
```
show interfaces serial 0/0/0
```
