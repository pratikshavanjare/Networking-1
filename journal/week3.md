# Switches, L2, and L3 Explained

##  What is a Switch?
A **network switch** is a device that connects multiple computers, servers, or devices within the same network (like a LAN).  
- It forwards data (frames/packets) only to the specific device it’s meant for, not to all devices.  
- This makes communication faster and more secure than using a hub.  

---

##  Layer 2 (L2) Switch
- Works on **Data Link Layer** of the OSI model.  
- Uses **MAC addresses** to forward data.  
- Mainly used in **Local Area Networks (LANs)**.  
- Example: Connecting PCs inside an office network.  

👉 **Limitations:**  
- Cannot communicate between different networks (only works within the same network).  

---

##  Layer 3 (L3) Switch
- Works on **Network Layer** of the OSI model.  
- Uses **IP addresses** for forwarding data.  
- Can do **routing** between different networks (like a router).  
- Provides both **switching (L2)** and **routing (L3)** features.  

👉 **Use case:**  
- Large enterprise networks where you need both fast switching and inter-network communication.  

---

## Comparison between L2 & L3

| Feature            | L2 Switch (Data Link) | L3 Switch (Network) |
|---------------------|-----------------------|----------------------|
| **Layer**          | Layer 2 (MAC)        | Layer 3 (IP)        |
| **Uses**           | MAC Address          | IP Address          |
| **Function**       | Switching within LAN | Switching + Routing |
| **Speed**          | Faster, simple       | Slightly slower, more complex |
| **Example Use**    | Office LAN           | Enterprise networks with VLANs |

---


# VLAN and Trunk

## VLAN (Virtual Local Area Network)
- VLAN is a **logical network** created within a physical network.
- It allows devices to be grouped together even if they are not on the same physical switch.
- Each VLAN has its own **broadcast domain**, which improves security and reduces unnecessary traffic.

### Example:
- VLAN 10 → HR Department  
- VLAN 20 → IT Department  
- VLAN 30 → Finance Department  

Devices in VLAN 10 cannot directly communicate with VLAN 20 unless routing is configured.

---

## Trunk
- A **Trunk** is a link between switches that carries traffic of **multiple VLANs**.
- It uses **tagging (IEEE 802.1Q)** to identify which VLAN the traffic belongs to.
- Trunks are used to allow VLAN information to travel across different switches.

### Example:
- Switch A (VLAN 10, VLAN 20) ↔ **Trunk Link** ↔ Switch B (VLAN 10, VLAN 20)  
- The trunk link carries both VLANs' traffic between the switches.

---

## Key Difference
| Feature         | VLAN                                   | Trunk                                    |
|-----------------|----------------------------------------|------------------------------------------|
| Definition      | Logical segmentation of a network       | Link that carries multiple VLANs         |
| Scope           | Works within a single switch            | Connects multiple switches               |
| Broadcast Domain| Separate for each VLAN                  | Can carry multiple VLANs across switches |
| Example         | VLAN 10 = HR, VLAN 20 = IT              | Trunk link between Switch A and Switch B |


