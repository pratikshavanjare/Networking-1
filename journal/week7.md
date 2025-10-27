## Access Control List (ACL)

###  What is ACL?
ACL is stands for Access Control List and It is used as a rule in router or switch for blocking any website, subnet, or controlling traffic and also improves security. It is also known as Packet Filtering Firewall.

---

###  How ACL Works

This will complete in 5 steps that are below -

1. Packet Arrives - When a packet reaches the router, the ACL examines it.  
2. Check Rule 1 - Router will check the packet's details - like source ip, destination ip, protocol or port.
3. Check Rule 2 - The ACL compares the packet with its list of rules from top to bottom.  
4. Check Rule 3 - According to the rule, if rule matches it will permit otherwise it will denied the packet.
5. Implicit Deny All - If no rule matches, the packet is automatically denied.

---

###  Example
Suppose, we want to block on device from accessing our network for that we can use ACL rule to deny that IP and allow others.
So, only traffic from allowed IPs will pass through the router interface.

---

###  Types of ACL
There are two types of ACL -
1. Standard ACL
2. Extended ACL

#### 1. Standard ACL - 
It is used to allow or block traffic based only on the source IP address. It is simpler but less flexible than extended ACL. 

##### Characteristics
- It checks where data is coming from.
- Number range : 1-99 and 1300-1999.
- It always usually placed near to the destination.
- It is used only when you want to block or allow entire network.

#### 2. Extended ACL
It will do the same thing controlling network traffic but more precisely. It will use source IP as well as Destination IP, protocol and port number for filtering traffic.

##### Characteristics
- Number Range : 100-199 and 2000-2699.
- It is more complex amd detailed traffic control.
- It always usually placed near to the Source.
- It is used only when you want to block or allow specific protocol or port on a network.

#### Reference [Day 15](https://claude.ai/public/artifacts/bd93a197-c4e7-4055-8fb8-244f36c6d823)



## LAN Switching

###  What is LAN Switching?
It is a process used in computer networks to transfer data within a Local Area Network (LAN).  It allows multiple devices like PCs, printers, and servers to communicate efficiently using network switches.

---

###  How Switches Work
A switch works at Layer 2 (Data Link Layer) of the OSI model. It uses MAC addresses to decide where to send each data frame.

**Basic steps:**
1. The switch receives a frame from one device.  
2. It reads the source and destination MAC addresses.  
3. Based on its MAC address table, it sends the frame to the correct device.  

This process helps in **reducing collisions** and improving **network performance**.

---

###  Switch Learning Process
Switches build a **MAC Address Table** (also called a CAM table) to remember which device is connected to which port.

**Learning Steps:**
The whole process will complete in four steps -
1. **Learning:**  
   When a frame enters a switch, it notes the **source MAC address** and the **port** it came from.  
   → Adds this info to the MAC table.
2. **Forwarding:**  
   When the switch receives another frame, it checks the **destination MAC** in its table.  
   → If it knows the port, it sends the frame there.
3. **Flooding:**  
   If the destination MAC is **unknown**, the switch sends (floods) the frame to all ports except the one it came from.
4. **Aging:**  
   Entries in the MAC table are **removed after a time** if no traffic is seen from that MAC.

---

###  Frame Forwarding Methods
Switches can forward frames in different ways:

| Method | Description |
|---------|--------------|
| **Store-and-Forward** | The switch receives the entire frame, checks for errors (CRC), and then forwards it. Most accurate but slightly slower. |
| **Cut-Through** | The switch starts forwarding as soon as it reads the destination MAC. Faster but less error-checking. |
| **Fragment-Free** | A balance between both — it checks the first 64 bytes for errors before forwarding. |

---
#### Reference [Day 16](https://claude.ai/public/artifacts/c07e6c2a-f9ae-4abd-a263-adb67b666bc9))
