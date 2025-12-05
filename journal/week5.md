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


---



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

----------------------------------------------------------------------


