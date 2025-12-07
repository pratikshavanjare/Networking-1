# Firewall & Router Redundancy

## 1. FIREWALL

A firewall is like a security guard for your network. It checks every packet entering or leaving and decides whether to allow or block it based on rules. It protects the network from hackers, malware, and unauthorized access.

**Important Firewall Commands**

**1. Allow specific traffic**
```
1. Allow specific traffic
```

**2. Block specific IP**
```
access-list OUTSIDE-IN deny ip host 10.10.10.5 any
```

**3. View firewall rules**
```
show access-list
```

**4. Enable firewall on interface**
```
zone security INSIDE
zone security OUTSIDE
```

**5. Bind interface to zone**
```
interface g0/0
 zone-member security INSIDE
```

---------------------------------------------------------------------

## 2. Router Redundancy

Router redundancy means having a backup router ready so your network doesn’t go down if the main router fails. It gives high availability and continuous internet access.

**Most common redundancy protocols:**

- HSRP (Cisco only)
- VRRP (Vendor-neutral)
- GLBP (Cisco, load-balancing)

### 1. HSRP Commands

**Create HSRP group**
```
interface g0/0
 standby 1 ip 192.168.1.1
```

**Set priority (higher = active router)**
```
standby 1 priority 120
```

**Preempt (take back active role when healthy)**
```
standby 1 preempt
```

**Check HSRP status**
```
show standby
```

### 2. VRRP Commands

**Configure VRRP**
```
interface g0/0
 vrrp 5 ip 192.168.1.1
```

**Set priority**
```
vrrp 5 priority 110
```

**Enable preempt**
```
vrrp 5 preempt
```

### 3. GLBP Commands

**Configure GLBP**
```
interface g0/0
 glbp 10 ip 192.168.1.1
```

**Priority**
```
glbp 10 priority 150
```

**Preempt**
```
glbp 10 preempt
```

**View GLBP**
```
show glbp
```


