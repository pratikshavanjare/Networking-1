# Routing and Its Types

## What is Routing?
Routing is one of the most important concepts in networking because it decides how data travels from one point to another. Here, I will explain routing in a very simple way—what it is, why it is needed, and how different routing protocols like RIP, OSPF, EIGRP, and BGP work.

Whenever we open a website or send a message, that data doesn’t go in a straight line. It has to pass through different devices and networks. so here, Routing helps choose the best and safest path for that data.

You can think of it like Google Maps.
Your data is like a car, the network cables are the roads, and the routers are the traffic signals or intersections. Just like Google Maps tells us the fastest route, routers use a routing table to guide the data to the correct destination.

   <img width="450" height="450" alt="Screenshot 2025-12-06 203246" src="https://github.com/user-attachments/assets/945dfc2a-7d85-44e1-9fd9-7cd8467b576d" />


---

## Types of Routing

Routing is mainly of two types: Static Routing and Dynamic Routing.

### 1. Static Routing

In static routing, the network admin has to manually add the routes.

It’s simple to use in small networks and is very secure because nothing changes automatically.the router doesn’t have to calculate anything.
Since the routes are already manually entered, the router just follows them.It is stable and predictable because nothing changes on its own. We change it only when we want.

But the problem is— if the network grows or a link goes down, you must manually update everything.
So static routing works well for small, fixed networks.

---

### 2. Dynamic Routing

Here the routers automatically learn and update routes using protocols like RIP, OSPF, EIGRP, and BGP.
It’s great for medium and large networks because routers can adjust themselves when the network changes.
It also provides backup paths automatically.
The only downside is that it uses more CPU and memory, and it’s a bit more complex to configure compared to static routing.

---

## Troubleshooting Steps

### 1. Static Routing Issues

1. Check if the static route is entered correctly (IP, subnet mask, next-hop).  
2. Verify connectivity with `ping` or `traceroute`.  
3. Ensure the interface is **up**.  
4. Look at the **routing table** to confirm the route exists.  

### 2. Dynamic Routing Issues

1. Check if the routing protocol is enabled on the correct interfaces.  
2. Verify neighbor/adjacency relationships (`show ip ospf neighbor`, `show ip eigrp neighbors`).  
3. Check for mismatched configurations (like wrong area in OSPF, wrong AS in EIGRP).  
4. Look for network flaps or unstable links.  
5. Use debug commands (`debug ip routing`) carefully to see updates.  


#### Reference [Day 1](https://claude.ai/public/artifacts/1921e117-1ea7-41d9-aefb-c5beb03b1c6b)
---



# Interdomain & Intradomain Routing  
**Routing** is the process of selecting the best path for data packets to travel across networks.

##  Types of Routing

### 1. Intradomain Routing
- Used **within a single organization or autonomous system (AS)**.  
- Focuses on efficient routing inside the network.  
- Examples: **RIP, OSPF, EIGRP**

### 2. Interdomain Routing
- Used **between different organizations or autonomous systems**.  
- Focuses on routing between multiple networks on the Internet.  
- Example: **BGP (Border Gateway Protocol)**

     <img width="500" height="450" alt="image" src="https://github.com/user-attachments/assets/ea6e24ea-898c-4c54-8981-a1dab05c6133" />


---

##  RIP - Routing Information Protocol

RIP is one of the oldest routing protocols.
It is simple, uses hop count as its metric, and works well in small networks.

- **Oldest IGP:**
RIP is one of the earliest protocols used for routing inside organizations.

- **Distance Vector Protocol:**
Hop Count Metric:
RIP chooses the best path based on hop count. Maximum 15 hops are allowed.

- **Updates every 30 seconds:**
RIP sends its full routing table to all neighbors every 30 seconds.

- **UDP port 520:**
It uses UDP port 520 for sending routing updates.

- **Bellman–Ford Algorithm:**
RIP uses the Bellman–Ford algorithm to calculate paths.

- **Supports RIPv1 & RIPv2:**
“RIPv1 is classful; RIPv2 supports subnet masks and is classless.”
 
### RIP Timers

- **Update Timer – 30 sec**

   Every 30 seconds, RIP sends its full routing table to all neighbors.

- **Invalid Timer – 180 sec**

   If no update is received for 180 seconds, the route is marked as invalid — basically, not trusted.

- **Holddown Timer – 180 sec**

  When a route fails, the router waits 180 seconds before accepting any new information about that route to avoid false updates.

- **Flush Timer – 240 sec**

 After 240 seconds, the unreachable route is completely removed from the routing table.


 ### Limitations

- It doesn’t consider bandwidth or delay.
- Older version doesn’t support subnet masks.
- Every 30 sec, full table broadcast causes extra traffic.
- Sending full routing tables regularly consumes bandwidth.
- Anything beyond 15 hops is unreachable.

### Solutions

- **Split Horizon:** Don’t send routes back where they came from.
- **Route Poisoning:** Mark failed routes as 16 (unreachable).
- **Poison Reverse:** Send back failed route with metric 16 to confirm failure.
- **Hold-down Timer:** Wait before accepting new route info to avoid wrong
updates.


 

###  Troubleshooting Tips
- Check network connectivity (`ping`, `tracert`)  
- Verify RIP configuration (correct network statements)  
- Ensure no route loops exist  
- Use `show ip route` and `debug ip rip` (in Cisco devices) for diagnosis  

     <img width="500" height="450" alt="Screenshot 2025-12-06 203519" src="https://github.com/user-attachments/assets/ca0f04b5-7b6b-4b54-8408-31ffecbc8dea" />


---


#### Reference [Day 2](https://claude.ai/public/artifacts/a28f54e1-e72b-4bdd-af38-6201ec24618a)




