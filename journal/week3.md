# Switches, L2, and L3 Explained

##  What is a Switch?

A switch is like a smart traffic manager for your network. Imagine you have several computers or devices in your home or office. When one device wants to send data to another, the switch makes sure that data goes only to the device it’s meant for, instead of sending it to everyone.

Because of this, the network is faster and safer compared to using a hub, which just broadcasts data to all devices. So, a switch helps devices talk to each other efficiently without creating unnecessary traffic. 

---

##  Layer 2 (L2) Switch

A Layer 2 (L2) switch is like a smart helper inside a single network (like an office LAN). It looks at the MAC addresses of devices—basically their unique ID cards—to decide where to send the data. So if one computer wants to talk to another, the L2 switch delivers the message directly, making the network fast and efficient.

Limitations: The L2 switch only works within the same network. It can’t send data to another network—that’s a job for a router.

---

##  Layer 3 (L3) Switch
A Layer 3 (L3) switch is like a super-smart switch that can do more than just connect devices in the same network. It works on the Network Layer, which means it looks at IP addresses instead of MAC addresses. This allows it to send data between different networks, just like a router does.

Basically, an L3 switch combines the speed of a normal Layer 2 switch with the ability to route traffic across networks, so it’s great for larger office or campus networks where multiple networks need to communicate efficiently.


 **Use case:**  
- A **Layer 3 switch** is used in large networks to provide **fast communication within a network** and **routing between different networks**, combining the roles of a switch and a router in one device.
---

   <img width="450" height="450" alt="Screenshot 2025-12-06 201525" src="https://github.com/user-attachments/assets/487e09e4-b9c0-47bf-a892-ad8ac95ade28" />


## Comparison between L2 & L3

| Feature                | Layer 2 Switch                                                                                                                                                          | Layer 3 Switch                                                                                                                                                           |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Primary Function**   | Operates based on **MAC addresses**. It forwards data within the same network using hardware addresses. Essentially, it’s great for connecting devices in the same LAN. | Operates using **IP addresses** to route data between different networks, but can also use MAC addresses for local forwarding. It’s like a switch and a router combined. |
| **VLANs**              | Cannot route data between VLANs. Each VLAN is isolated, and a Layer 2 switch only forwards traffic within the same VLAN.                                                | Can route traffic between VLANs (inter-VLAN routing). This allows communication across different VLANs without needing a separate router.                                |
| **Cost**               | Generally **lower**: $50–$500.                                                                                                                                          | More **expensive**: $500–$10,000, because it has routing capabilities built in.                                                                                          |
| **Performance**        | **Very fast** because it only switches data within a LAN using MAC addresses.                                                                                           | Slightly slower than Layer 2 switches, as it also processes IP routing. Still faster than traditional routers.                                                           |
| **Addressing**         | Uses **MAC addresses** (48-bit) for identifying devices in the network.                                                                                                 | Uses **IP addresses** (32-bit for IPv4 or 128-bit for IPv6) for routing between networks, and also uses MAC addresses for local switching.                               |
| **Broadcast Domain**   | Single broadcast domain per VLAN. Each VLAN isolates broadcast traffic.                                                                                                 | Separate broadcast domains per subnet or VLAN. It can manage multiple VLANs efficiently.                                                                                 |
| **Inter-VLAN Routing** | **Not supported** natively. Requires an external router to allow VLANs to communicate.                                                                                  | **Built-in**. Layer 3 switches can route traffic between VLANs without needing an extra router.                                                                          |
| **Routing Protocols**  | **Not supported.** Cannot participate in routing decisions.                                                                                                             | Supports **routing protocols** like **Static Routing, OSPF, EIGRP, BGP**, etc., for dynamic or large network routing.                                                    |
| **Complexity**         | **Simple configuration**; plug and play for small LANs.                                                                                                                 | **More complex**; requires understanding IP addressing, routing, and VLANs.                                                                                              |
| **Use Case**           | Ideal for **small networks** or single subnet environments, like offices or small buildings.                                                                            | Ideal for **enterprise networks** with multiple subnets, VLANs, and inter-VLAN communication.                                                                            |


---


# VLAN and Trunk

## VLAN (Virtual Local Area Network)

A VLAN is a way to logically divide a physical network into multiple smaller networks.
Even if devices are connected to the same switch, they can be placed into different VLANs to separate traffic, improve performance, and increase security.

**Why VLANs?**

- Devices inside one VLAN form a single broadcast domain.
- Traffic from one VLAN does not reach another VLAN unless a router (Layer-3 device) is involved.
- This helps organize networks—such as separating departments like HR, IT, Finance, etc.

**Simple Example**
```
VLAN	             Purpose
VLAN 10          	HR Department
VLAN 20          	IT Department
VLAN 30          	Finance Department
```

Devices in VLAN 10 cannot directly talk to devices in VLAN 20 without routing.

**Benefits of VLANs*:**

- **Improved Security –** Sensitive departments remain isolated.

- **Cost Reduction –** No need for separate physical switches for every group.

- **Better Performance –** Less broadcast traffic.

- **Smaller Broadcast Domains –** Reduces unnecessary network chatter.

- **Efficient IT Management –** Easier to manage groups of users.


**VLAN Frame Tagging (802.1Q)**

VLAN tagging is the process of adding a small identifier (tag) inside an Ethernet frame.
This tag tells switches which VLAN the frame belongs to, allowing multiple VLANs to travel over the same physical connection.

   <img width="600" height="550" alt="image" src="https://github.com/user-attachments/assets/98227500-6275-4101-aed8-171feb9e16fb" />


-------------------------------------------------------------

## Trunk
- A **Trunk** is a link between switches that carries traffic of **multiple VLANs**.
- It uses **tagging (IEEE 802.1Q)** to identify which VLAN the traffic belongs to.
- Trunks are used to allow VLAN information to travel across different switches.

### Example:
- Switch A (VLAN 10, VLAN 20) ↔ **Trunk Link** ↔ Switch B (VLAN 10, VLAN 20)  
- The trunk link carries both VLANs' traffic between the switches.


     <img width="600" height="550" alt="Screenshot 2025-12-06 202008" src="https://github.com/user-attachments/assets/1a7fc8c5-adbf-4b3b-9cfd-52104eb00104" />


------------------------------------------------

## Key Difference

| **Feature**                            | **VLAN**                                                                                                                                                                                                                                         | **Trunk**                                                                                                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Definition**                         | A VLAN (Virtual Local Area Network) is a way to logically divide a physical network into multiple smaller, isolated networks. Devices in different VLANs act as if they are on different switches, even if physically connected to the same one. | A trunk is a special type of link between switches (or switch-to-router) that carries traffic for **multiple VLANs** at the same time using VLAN tagging (802.1Q). |
| **Purpose**                            | To separate traffic, improve security, reduce broadcast domains, and organize network segments (e.g., separating departments).                                                                                                                   | To allow VLANs to extend across multiple switches so devices in the same VLAN can communicate even if located on different switches.                               |
| **Scope**                              | Usually operates **within a single switch**—it controls how ports are grouped logically.                                                                                                                                                         | Operates **between switches** (or switch-router). It allows VLAN information to travel across the network.                                                         |
| **How It Works**                       | Each port is assigned a VLAN ID. Devices inside the same VLAN share the same broadcast domain.                                                                                                                                                   | Frames are tagged with VLAN IDs before they travel over the trunk link, allowing multiple VLANs to share the same physical cable.                                  |
| **Broadcast Domain**                   | Each VLAN is its own broadcast domain, meaning broadcasts stay inside that VLAN only.                                                                                                                                                            | A trunk does *not* create a broadcast domain; instead, it **carries multiple VLAN broadcast domains** across switches.                                             |
| **Example**                            | VLAN 10 = HR                                                                                                                                                                                                                                     |                                         


-----------------------------------------------------------------------------------
# Spanning Tree Protocol (STP)

## What is Spanning Tree Protocol?

STP (Spanning Tree Protocol) is a network protocol used in switches to prevent loops in a Layer-2 network.
When multiple switches are connected with redundant links, loops can easily form — STP stops this by logically creating one single active path and blocking the others.

## Why do we need STP ?

- ** Prevents Network Loops**
Without STP, redundant links cause broadcast storms, multiple frame copies, and MAC table instability.

- **Keeps Backup Paths Ready**
STP blocks extra paths only during normal operation.
If the main path fails, STP unblocks a backup path, restoring connectivity.

- **Automatically Works**
No manual intervention is needed — STP constantly monitors and adjusts the network.

- **Built-In on All Modern Switches**
Most managed switches support STP, RSTP, MSTP, etc.

## How STP works (short steps)

**Step 1: Elect the Root Bridge (Root Switch)**

All switches exchange BPDU messages.
The switch with the lowest bridge ID becomes the Root Bridge.
This switch becomes the “central reference point” of the network.

**Step 2: Find the Best Paths to the Root**
Each switch calculates the shortest/fastest path to the root switch.
Example:
SW1 → Root: 100 Mbps link
SW2 → Root: 1 Gbps link
The switch prefers the lowest cost (fastest path).

**Step 3: Block Redundant Paths**

Once the best paths are chosen:
STP blocks ports that lead to loops.
Only one active path remains.
Backup paths stay in a blocking/standby state.
This prevents loop formation while still keeping redundancy.

<br>

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/1e8eac91-8818-48e3-bff7-7b76c59886e9" />


---



#### Reference [Day 1](https://claude.ai/public/artifacts/83161f5d-1c14-4ed0-8720-8f0c4d1c951b)

