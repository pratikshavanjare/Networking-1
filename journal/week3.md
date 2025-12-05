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



# Spanning Tree Protocol (STP)

## What is Spanning Tree Protocol?

STP (IEEE 802.1D) prevents **switching loops** in Ethernet networks by creating a single active path between switches and blocking redundant links. It ensures a loop-free Layer 2 topology.

## Key STP concepts

* **Root Bridge**: The central reference switch (lowest bridge ID).
* **Bridge ID (BID)**: Combination of priority + MAC address used to elect the root.
* **Root Port (RP)**: On non-root switches, the port with the best path to the Root Bridge.
* **Designated Port (DP)**: The port on a network segment chosen to forward frames to that segment.
* **Blocked Port**: Port that does not forward frames (prevents loops).
* **Path Cost**: Metric based on link speed used to choose best paths.
* **Port States**: (Legacy) Blocking, Listening, Learning, Forwarding (RSTP shortens these).

## How STP works (short steps)

1. **Election**: All switches exchange BPDUs. Lowest Bridge ID becomes the Root Bridge.
2. **Root Port selection**: Each non-root switch selects one Root Port (lowest path cost to root).
3. **Designated Port selection**: For each LAN segment, the switch with lowest path cost to root becomes the Designated Bridge; its port is the Designated Port.
4. **Blocking**: Any other ports that would create loops are put into a Blocking state.
5. **Convergence**: After timers, ports move to Forwarding or remain Blocked; traffic flows without loops.

> Note: **RSTP (802.1w)** is faster and commonly used today; it keeps the same core ideas but converges quicker.

## Real examples (simple topologies)

* **Triangle of 3 switches (A—B—C with extra link A—C)**

  * Root elected (lowest BID), other switches pick root ports. One of the triangle links will be blocked to avoid a loop.
* **Access switch with two uplinks to distribution switches**

  * One uplink forwards, the other is blocked; if the active uplink fails, STP unblocks the backup link.

### Example Cisco-ish commands 

```
show spanning-tree            # view STP status and topology
show spanning-tree root       # show root bridge info
show spanning-tree brief      # quick port states
spanning-tree vlan 1 priority 4096   # lower priority to make this switch root
```

## Common troubleshooting (short fixes)

* **Symptom: Broadcast storms / loops**

  * Check for multiple active links that should be blocked. Use `show spanning-tree`.
* **Symptom: Slow convergence after link fail**

  * Use RSTP (rapid) or tune timers; enable uplink fast/portfast on access ports if appropriate.
* **Symptom: Wrong root bridge (not desired switch)**

  * Change bridge priority on preferred root (`spanning-tree priority`), or adjust MAC tiebreakers.
* **Symptom: Port stays blocking unexpectedly**

  * Verify BPDU reception on that port, check port cost and link speed, ensure no STP mode mismatch.


---



#### Reference [Day 1](https://claude.ai/public/artifacts/83161f5d-1c14-4ed0-8720-8f0c4d1c951b)

