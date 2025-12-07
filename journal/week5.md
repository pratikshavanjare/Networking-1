# 🛰️ OSPF (Open Shortest Path First)

##  What is OSPF?

OSPF is a link-state routing protocol that uses Dijkstra’s algorithm to find the shortest and most efficient path.
It works inside an organization and is widely used because it is fast, scalable, and reliable.

---

##  Key Concepts

- **Link-State Routing Protocol** – OSPF keeps a full map of the network topology, not just neighbor information.

- **Interior Gateway Protocol (IGP)** – It works inside one Autonomous System, just like RIP or EIGRP.

- **Classless Protocol**– it supports VLSM and CIDR, so IP addressing is flexible.

- **Protocol Number:** Routers identify OSPF packets using protocol number 89.

- **Administrative Distance:** OSPF has AD 110, better than RIP but lower than EIGRP.

- **Uses Dijkstra’s SPF Algorithm** – This algorithm calculates the shortest, most efficient path.

- **Cost-Based Metric** – OSPF chooses the best path based on cost, which is derived from bandwidth.
Higher bandwidth = lower cost = better path.
where RIP select paths only uses Hop count, it can't able to find the best path like bandwidth.

- **Vendor-Neutral (Open Standard)**– OSPF is open standard, so it works on Cisco, Juniper, Linux, everything

- **Hierarchical Design** – OSPF uses areas for better scalability and performance.

   So overall, OSPF is fast, reliable, scalable, and perfect for medium to large networks.

---

##  How OSPF Works
1. Routers discover neighbors using **Hello packets**.  
2. They exchange **LSAs** to learn the full network topology.  
3. Each router builds the same **Link-State Database (LSDB)**.  
4. Using **Dijkstra’s algorithm**, OSPF calculates the **shortest path**.  
5. Routing tables are updated with the best routes.

---

##  OSPF Area Concept

   OSPF doesn’t put the whole network into one big area. Instead, it divides the network into multiple areas to reduce overhead and improve performance.

- **Backbone – Area 0**

   Area 0 is the main backbone of OSPF.
   All other areas must connect to Area 0.
   It acts like the central highway of the network.


- **Benefits of Using Areas**

1. **Smaller LSDB per area:**
   Each router stores less information, reducing memory usage.

2. **Reduced LSA flooding:**
   Updates don’t travel everywhere, only within the same area.

3. **Faster SPF Calculation:**
   Because routers calculate paths for their own area, not the whole network.

4. **Better Organization:**
   Helps manage large networks cleanly.


## Five OSPF Packet Types

1. **Hello Packets**
   Routers send Hello packets every 10 seconds to check if neighbors are alive.


2. **DBD (Database Description)**

- Summarizes LSDB during adjacency formation

- Contains LSA headers

3. **LSR (Link-State Request)**

- Requests missing or outdated LSAs from neighbors

4. **LSU (Link-State Update)**

   Sends the actual LSAs containing topology details.

5. **LSAck (Link-State Acknowledgment)**

   Confirms receipt of LSUs for reliable delivery


## OSPF Metrics & Path Selection

- **Cost Formula**
  
  Cost = Reference Bandwidth ÷ Interface Bandwidth
 
  Default Reference Bandwidth = 100 Mbps

**Examples**
  1 Gbps → Cost 1

  100 Mbps → Cost 1

  10 Mbps → Cost 10

- **Path Selection**
  
  Lower cost = better path

  Sum of costs along entire path

  Equal-cost paths allow load balancing

- **SPF Algorithm**
  
  LSDB → Dijkstra’s SPF → Shortest Path Tree → Routing Table

## Limitations

- OSPF is more complex compared to RIP.

- It needs more CPU and memory.

- Not recommended for very small networks where RIP or static routing is enough.

- Area design is important; bad design = performance issues.

- Frequent SPF recalculations can slow down the router.

- OSPF does not scale well unless the network follows proper Area 0 hierarchy.


## Solutions

- Use proper area design to avoid unnecessary complexity.

- Always create a hierarchical structure with Area 0 in the center.

- Adjust SPF timers if needed to reduce CPU load.

- Use hardware that has enough CPU and memory to handle OSPF.

- Divide large networks into multiple areas to control LSA flooding.

<img width="1422" height="602" alt="image" src="https://github.com/user-attachments/assets/41b64ed9-07a8-4602-bc1d-747ded069916" />
 


#### Reference [Day 1](https://claude.ai/public/artifacts/fbf70cac-6f1a-41cf-adcc-6336e3136ab5?fullscreen=true)

------------------------------------------------------------------------



# EIGRP (Enhanced Interior Gateway Routing Protocol)

EIGRP is a Cisco routing protocol that finds the best path very quickly.
It uses a smart algorithm called DUAL, which helps it avoid loops and gives faster convergence compared to RIP and OSPF.

---

## 2. Characteristics of EIGRP
- Developed by Cisco Systems
- It is a Cisco proprietary, classless routing protocol that supports
VLSM
- Works as a hybrid routing protocol (Advanced Distance Vector)
combining features of distance vector and link-state
- Provides fast convergence using the DUAL algorithm (Diffusing
Update Algorithm)
- Uses composite metric based on bandwidth, delay, load, and
link reliability
- Uses Autonomous System (AS) numbers to group routers
- Supports multiple network layer protocols (IP, IPX, AppleTalk)
- Uses RTP (Reliable Transport Protocol) for reliable and
synchronized updates
- Sends reliable multicasts to 224.0.0.10
- It uses port number 88
  
---

## 3. How EIGRP Works

1. **Neighbor Discovery**
   - Routers send Hello packets to find neighbors
   - Hello sent every 5 seconds (default)
   - Neighbors must be in same subnet and same AS number

2. **Topology Table**
   - Stores all learned routes with metrics
   - Contains Successor (best route) and Feasible Successor (backup
route)
   - Only the best route is placed in the routing table

3. **Route Selection**
   - Uses DUAL algorithm
   - Ensures loop-free routing and fast convergence
   - Chooses best path and prepares backup path

4. **Neighbor Table**
   - Lists all EIGRP neighbors
   - Stores neighbor IP, interface, and timers
   - Tracks reachability

---

## 4. EIGRP Packet Types

**1. Hello Packets**

   - Hello packets are used to find and maintain neighbors.
   - EIGRP sends them every 5 seconds, and they go to a multicast address.
   - If routers stop receiving Hello packets, they assume the neighbor is down.

**2. Update Packets**

   - Update packets carry the actual routing information.
   - They are only sent when something changes, not all the time.
   - Updates are reliable, so they need an ACKnowledge.

**3. Query Packets**

   - Query packets are sent only when a router loses a route.
   - The router basically asks neighbors, ‘Do you have another path for this network?’
   - Every Query must be answered.

**4. Reply Packets**

   - Reply packets are the answers to Query packets.
   - They contain the alternative route information, if available.
   - Replies are unicast back to the router that asked.

**5. ACK Packets**

   - ACK packets are simple acknowledgements.
   - They confirm that an Update or Reply was received.
   - They look like empty Hello packets.

<img width="1540" height="626" alt="Screenshot 2025-12-06 203745" src="https://github.com/user-attachments/assets/68c8230f-28dd-4965-9d3a-7ebdd9e72557" />



#### Reference [Day 2](https://claude.ai/public/artifacts/c030298c-25c3-490e-a1ff-eb03eda1f418?fullscreen=true)
----------------------------------------------------------------------


# BGP (Border Gateway Protocol)

BGP is the routing protocol that runs the entire internet.
Whenever data travels between different companies or ISPs, it uses BGP. It is Path-Vector.
It doesn’t look for the shortest path — it looks for the most reliable and policy-based path.

## Characteristics 

1. **Uses TCP Port 179** -
BGP uses TCP, so it is very reliable.
Unlike RIP/OSPF which use UDP, BGP forms stable sessions.

2. **Runs the Global Internet** -
All ISPs like Jio, Airtel, Google, Amazon — everyone uses BGP to exchange routes.

3. **Focus on Reachability** -
BGP doesn’t care about shortest path.
It only cares if a destination is reachable and follows policies.

4. **Highly Scalable** -
It can handle hundreds of thousands of routes — that’s why the internet depends on it.

5. **Classless Protocol** -
Supports VLSM and CIDR to reduce routing table size.

6. **Policy-Based Routing** -
With BGP, companies can choose routes based on business rules — like cost, security, priority.

7.**Slow Convergence** -
BGP is slower to update because it prioritizes stability over speed.

## eBGP vs iBGP

**eBGP** (External BGP) is the version of BGP used between different autonomous systems, meaning between completely separate networks—like when an enterprise network connects to an ISP, or when two ISPs exchange routes. Because eBGP works across independent networks, it modifies the AS path to prevent loops and usually expects the neighbor to be directly connected. Think of eBGP as two different organizations exchanging routing information so they know how to reach each other’s networks.

**iBGP** (Internal BGP), on the other hand, is used within the same autonomous system. It doesn’t change the AS path or the next-hop because all routers belong to the same internal network. Instead, its job is to distribute the external routes learned from eBGP throughout the inside of the AS. You can think of iBGP as coworkers inside the same organization sharing information so everyone knows how to reach destinations outside the company. Because iBGP doesn’t modify the AS path, it requires a full mesh of peers—or the use of route reflectors—to prevent routing loops.


## BGP Path Attributes

- **AS Path:** Shows which ASes the route has passed through. Helps avoid loops.

- **Next-Hop:** Tells the router where to send the traffic next.

- **Local Preference:** Used inside the AS. Higher value = preferred exit path.

- **MED:** Suggests which link other ASes should use to enter your network.

- **Weight:** Cisco-only. Highest weight wins on that router.

## Limitation

**1. Slow convergence**

When a link goes down, BGP takes a long time to update routes. This can cause temporary internet delays or outages.

**2. No built-in security**

BGP trusts all route updates, making it vulnerable to route hijacks or accidental misconfigurations unless extra security tools are used.

**3. Complex to configure and manage**

BGP has many policies and settings. Managing it, especially in large networks, can be hard and error-prone.

**4. Not performance-based**

BGP does not pick routes based on speed or latency. It chooses paths based on rules and policies, not on which path is actually the fastest.

**5. iBGP scalability issues**

Inside a large network, iBGP requires many peer connections. Without route reflectors or confederations, it doesn’t scale well.


## Solution 

**1. Slow convergence → Use faster failover techniques**

BGP can take a long time to detect failures, so using faster failover tools helps keep the network stable. One common solution is BFD (Bidirectional Forwarding Detection), which detects link failures in milliseconds and triggers BGP to react quickly. Network administrators can also tune BGP timers or use route damping to prevent frequent route changes from causing instability. These techniques together help BGP recover faster when something goes wrong.

**2. No built-in security → Add external security measures**

Since BGP does not verify whether received routes are legitimate, adding security layers is essential. Tools like RPKI help ensure that the routes being advertised actually belong to the correct owner. Administrators also use prefix filters, max-prefix limits, ACLs, and MD5 authentication to protect BGP sessions from hijacking or accidental leaks. These measures make BGP safer and more reliable on the global internet.

**3. Complex configuration → Use best practices and automation**

BGP is powerful but complicated, and manual configuration can lead to mistakes. Using standardized templates and clear routing policies helps keep setups consistent across devices. Automation tools such as Ansible or NetConf can deploy configurations across many routers at once, reducing human error. This makes managing BGP easier, especially in large networks.

**4. Not performance-based → Combine with other protocols or tools**

Because BGP selects routes based on policies rather than real-time performance, networks often combine it with other technologies to improve traffic flow. Traffic engineering techniques like adjusting local preference or MED values help control outbound and inbound paths. Solutions like SD-WAN, PBR, and QoS can steer traffic based on speed, latency, or application priority. This helps ensure that important traffic always takes the best path.

**5. iBGP scalability issues → Use hierarchical designs**

A full mesh of iBGP peers doesn’t scale well as networks grow, so hierarchical designs are used to make management easier. Route reflectors allow some routers to act as central points for iBGP updates, removing the need for every router to connect to every other one. Another solution is to use confederations, which break a large AS into smaller internal ASes to improve organization and scalability. These designs help large ISPs and enterprises manage BGP more efficiently.

<img width="1000" height="550" alt="image" src="https://github.com/user-attachments/assets/3173b586-4a42-4882-8eb1-8159e1336502" />



#### Reference [Day 3](https://claude.ai/public/artifacts/819e1cd3-57ee-4398-9446-513c3cce9597)
