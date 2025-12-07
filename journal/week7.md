## Access Control List (ACL)

###  What is ACL?
ACL is stands for Access Control List and It is used as a rule in router or switch for blocking any website, subnet, or controlling traffic and also improves security. It is also known as Packet Filtering Firewall.

---

###  How ACL Works

This will complete in 5 steps that are below -

1. **Packet Arrives** - When a packet reaches the router, the ACL examines it.  
2. **Check Rule 1** - Router will check the packet's details - like source ip, destination ip, protocol or port.
3. **Check Rule 2** - The ACL compares the packet with its list of rules from top to bottom.  
4. **Check Rule 3** - According to the rule, if rule matches it will permit otherwise it will denied the packet.
5. **Implicit Deny All** - If no rule matches, the packet is automatically denied.

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
- **Number range :** 1-99 and 1300-1999.
- It always usually placed near to the destination.
- It is used only when you want to block or allow entire network.

#### 2. Extended ACL
It will do the same thing controlling network traffic but more precisely. It will use source IP as well as Destination IP, protocol and port number for filtering traffic.

##### Characteristics
- **Number Range :** 100-199 and 2000-2699.
- It is more complex amd detailed traffic control.
- It always usually placed near to the Source.
- It is used only when you want to block or allow specific protocol or port on a network.

<img width="500" height="450" alt="image" src="https://github.com/user-attachments/assets/dc790b79-f845-460b-8a8b-ec627f13a324" />


#### Reference [Day 1](https://claude.ai/public/artifacts/bd93a197-c4e7-4055-8fb8-244f36c6d823)

----------------

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
#### Reference [Day 2](https://claude.ai/public/artifacts/c07e6c2a-f9ae-4abd-a263-adb67b666bc9)

-------------------------

##  WAN Technologies

###  What is WAN?
WAN is stands for Wide Area Network . It is a type ofnetwork that connects devices in large geographical areas like - cities,states, coutries or continents. 
Example - The Internet itself is the largest WAN.

---
##### Let's see some common wan technologies --

- **MPLS (Multiprotocol Label Switching)**
- **Leased Lines**
- **Broadband (DSL, Fiber, 4G/5G, etc.)**


###  MPLS (Multiprotocol Label Switching)

**What is MPLS?**  
MPLS is stands for Multiprotocol Label Switching . It is a routing techniques that directs data from one node to another using labels instead of IP addresses.   
It helps in faster and more reliable data delivery.

**How It Works:**
These will complete ini 4steps -
1. **Label Assignment** : Each data packet gets a label. 
2.** Label Switching** : Routers use that label to forward data quickly — no need to check full IP routing tables.
3. **Fast Forwarding** : The packet moves through the fastest path in the network.
4. **Label Removal** : When the packet reaches its end point, the label is removed and data is delivered.

**Benefits of MPLS:**

- Faster packet forwarding.  
- Better **Quality of Service (QoS)** for voice, video, and real-time traffic.  
- More reliable and secure than traditional Internet.  
- Easy to create **private networks** for different offices.

<img width="500" height="450" alt="Screenshot 2025-12-06 204618" src="https://github.com/user-attachments/assets/5c91c96f-aec4-4c93-9db2-a160a2a8c7b3" />


---

###  Leased Lines

**What is a Leased Line?**  
A Leased Line is a private Internet connection between two places, like a company’s offices. It gives the same speed all the time and is not shared with others.

** Benefits:**
- Symmetrical speeds (same upload and download).  
- No sharing with other users because it's a private connection.  
- Best for companies that need 24/7 data communication.
- It stays connected 24/7, making it fast and reliable.
- Used by banks and companies for safe data transfer.

<img width="500" height="400" alt="Screenshot 2025-12-06 204750" src="https://github.com/user-attachments/assets/699c53dd-cb06-4cbc-baa6-3ec9630d8cc7" />


---

###  Broadband WAN Connectivity

**What is Broadband?**  
Broadband is a high-speed Internet connection that lets you use the Internet for many things like watching videos, video calls, gaming, and downloading files.
It is called “broadband” because it can carry a large amount of data at once, which makes it much faster than old dial-up Internet.

**Types of Broadband Connections:**
- **DSL (Digital Subscriber Line)** – uses telephone lines.  
- **Cable Internet** – uses TV cables.  
- **Fiber Optic** – very fast and reliable.  
- **4G/5G Mobile Networks** – wireless broadband.

** Benefits:**
- Cost-effective and easy to install.  
- High-speed Internet access.  
- Supports multiple users and devices.  
- Suitable for remote work and small offices.

<img width="500" height="450" alt="Screenshot 2025-12-06 205209" src="https://github.com/user-attachments/assets/ea2f989b-df41-4441-8ec6-b26762be1ae0" />


#### Reference [Day 3](https://claude.ai/public/artifacts/376a8e93-7bdb-4cc1-9ab0-057fe128fc43)
---

