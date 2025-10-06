# Routing and Its Types

## What is Routing?
Routing is the process of selecting the best path for data to travel from source to destination across a network.  

---

## Types of Routing

### 1. Static Routing
- Routes are **manually configured** by the network administrator.  
- Simple, secure, but **does not change automatically** if the network changes.  
- Best for **small or stable networks**.  

#### ✅ When to Use (Examples)
- Small office/home networks.  
- Networks with very few routes.  
- When security and stability are more important than flexibility.  

---

### 2. Dynamic Routing
- Routers **automatically learn and update routes** using routing protocols.  
- Adapts to **network changes** (like link failure or new paths).  
- Best for **large and complex networks**.  

#### ✅ When to Use (Examples)
- Enterprise networks with many routers.  
- ISPs (Internet Service Providers) to connect large-scale systems.  
- Data centers where routes change frequently.  

---

## Troubleshooting Steps

### Static Routing Issues
1. Check if the static route is entered correctly (IP, subnet mask, next-hop).  
2. Verify connectivity with `ping` or `traceroute`.  
3. Ensure the interface is **up**.  
4. Look at the **routing table** to confirm the route exists.  

### Dynamic Routing Issues
1. Check if the routing protocol is enabled on the correct interfaces.  
2. Verify neighbor/adjacency relationships (`show ip ospf neighbor`, `show ip eigrp neighbors`).  
3. Check for mismatched configurations (like wrong area in OSPF, wrong AS in EIGRP).  
4. Look for network flaps or unstable links.  
5. Use debug commands (`debug ip routing`) carefully to see updates.  

---



# Interdomain & Intradomain Routing  
**Routing** is the process of selecting the best path for data packets to travel across networks.

## 🧭 Types of Routing
### 1. Intradomain Routing
- Used **within a single organization or autonomous system (AS)**.  
- Focuses on efficient routing inside the network.  
- Examples: **RIP, OSPF, EIGRP**

### 2. Interdomain Routing
- Used **between different organizations or autonomous systems**.  
- Focuses on routing between multiple networks on the Internet.  
- Example: **BGP (Border Gateway Protocol)**

---

## 🛰️ RIP - Routing Information Protocol
- **Type:** Distance-vector routing protocol  
- **Metric Used:** Hop count (max 15 hops)  
- **Updates:** Sent every 30 seconds  
- **Algorithm:** Bellman-Ford  
- **Versions:** RIP v1 (Classful), RIP v2 (Classless, supports subnet mask)  
- **Limitation:** Not suitable for large networks due to hop limit  

### 🧩 Troubleshooting Tips
- Check network connectivity (`ping`, `tracert`)  
- Verify RIP configuration (correct network statements)  
- Ensure no route loops exist  
- Use `show ip route` and `debug ip rip` (in Cisco devices) for diagnosis  

---

### 💡 Example Scenario
- **Intradomain:** RIP or OSPF used within a company’s LANs.  
- **Interdomain:** BGP used to connect the company network to an ISP.  



## For refernce --

(https://claude.ai/public/artifacts/1921e117-1ea7-41d9-aefb-c5beb03b1c6b)
(https://claude.ai/public/artifacts/a28f54e1-e72b-4bdd-af38-6201ec24618a)
