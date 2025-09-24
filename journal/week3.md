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



