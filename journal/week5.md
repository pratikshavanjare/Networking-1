# 🛰️ OSPF (Open Shortest Path First)

##  What is OSPF?
OSPF is a **dynamic routing protocol** used to find the best path for data through a network.  
It works within a single **Autonomous System (AS)** and uses the **Link State Routing** algorithm.

---

##  Key Concepts
- **Link-State Protocol:** Routers share information about their direct connections.  
- **Area:** OSPF divides networks into areas to optimize performance.  
- **Router ID:** Unique identifier (highest IP or manually assigned).  
- **LSA (Link-State Advertisement):** Packets used to share link information.  
- **Cost:** Metric used to choose the best route (based on bandwidth).  
- **DR/BDR:** Designated Router and Backup Designated Router reduce network traffic.

---

##  How OSPF Works
1. Routers discover neighbors using **Hello packets**.  
2. They exchange **LSAs** to learn the full network topology.  
3. Each router builds the same **Link-State Database (LSDB)**.  
4. Using **Dijkstra’s algorithm**, OSPF calculates the **shortest path**.  
5. Routing tables are updated with the best routes.

---

##  OSPF Areas
- **Area 0 (Backbone Area):** Core of all OSPF networks.  
- **Stub Area:** Does not accept external routes.  
- **NSSA (Not-So-Stubby Area):** Accepts limited external routes.

---

##  Real-World Example
Used in large enterprise networks or ISPs to efficiently route data between routers, ensuring **fast convergence** and **loop-free routing**.

---

##  Troubleshooting Tips
- Check **neighbor relationships** → `show ip ospf neighbor`  
- Verify **interfaces and area IDs**  
- Ensure **unique router IDs**  
- Check **hello/dead timer mismatches**  
- Use `show ip route ospf` to verify learned routes

---



# EIGRP (Enhanced Interior Gateway Routing Protocol)

## 1. What is EIGRP?
EIGRP is an **advanced distance-vector routing protocol** developed by Cisco.  
It combines **distance-vector and link-state features** (hybrid protocol).  
It is used for **routing within an autonomous system (AS)**.

---

## 2. Characteristics of EIGRP
- **Protocol Type:** Advanced Distance Vector (Hybrid)
- **Metric:** Bandwidth, Delay, Load, Reliability
- **Algorithm:** Uses **DUAL (Diffusing Update Algorithm)** for fast convergence
- **Supports:** IPv4 and IPv6, VLSM/CIDR
- **Neighbor Discovery:** Uses **Hello packets**
- **Routing Updates:** Only when topology changes (partial updates)
- **Authentication:** Supports MD5 authentication

---

## 3. How EIGRP Works
1. Routers send **Hello packets** to discover neighbors.
2. Builds **Neighbor Table** for directly connected routers.
3. Exchanges **Topology Table** information.
4. Uses **DUAL algorithm** to calculate the **best path** to each network.
5. Updates **Routing Table** with best paths.
6. Sends **partial updates** when network changes occur.

---

## 4. EIGRP Packet Types
| Packet Type         | Purpose |
|--------------------|---------|
| **Hello**           | Discover and maintain neighbors |
| **Update**          | Share routing information |
| **Query**           | Ask neighbors for a route when needed |
| **Reply**           | Response to Query |
| **Acknowledgment**  | Confirms receipt of Update, Query, or Reply |

---

