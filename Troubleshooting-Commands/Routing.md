# Routing – RIP, OSPF, EIGRP, BGP

Routing is basically how routers decide “Which path should I use to send data?”
Different routing protocols follow different rules to choose the best path.

**1. RIP (Routing Information Protocol)**

RIP is like an old-school GPS that only counts hops.
If a route has fewer hops, RIP thinks it’s better—even if it’s actually slower.
```
router rip
 version 2
 network 192.168.1.0
```

-------------------------------------------

**2. OSPF (Open Shortest Path First)**

OSPF is a smart protocol that uses cost, not hops.
Routers calculate the best path based on link speed.
It also divides networks into areas, which makes it scalable.
```
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
```

-------------------------------------------

**3. EIGRP (Enhanced Interior Gateway Routing Protocol)**

EIGRP is like a hybrid protocol—fast, efficient, and stable.
It uses a mathematical formula (metric) including bandwidth & delay to choose the best path.
Very popular in Cisco networks.
```
router eigrp 100
 network 192.168.1.0
```

------------------------------

**4. BGP (Border Gateway Protocol)**

BGP is the protocol of the internet.
It decides how data travels between different organizations, ISPs, countries.
It’s focused on policy, not speed—so you decide which path you prefer.
```
router bgp 65001
 neighbor 1.1.1.1 remote-as 65002
```


