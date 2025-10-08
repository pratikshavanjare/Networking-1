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

