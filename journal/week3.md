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


