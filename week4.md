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

👉 **In short:**  
- **Static Routing** → Simple, manual, good for small/stable networks.  
- **Dynamic Routing** → Automatic, adaptive, good for large/changing networks.  
