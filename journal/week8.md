## DAY 18

# Network Troubleshooting Tools

When the network doesn’t work properly, we use some basic tools to **check where the problem is** — whether it’s with the connection, the path, or the remote system.  
Here are the four most common tools used for troubleshooting.

---

## 1. **Ping – Test Connectivity**
**Purpose:**  
Ping helps us check if another device (like a server or router) is **reachable**.

**How it Works:**  
- It sends small packets called **ICMP Echo Requests** to the destination.  
- If the device is active, it replies with an **Echo Reply**.  
- From this, we can see the **response time** and whether packets are being lost.


## 2. **Traceroute / Tracert – Trace the Path**
**Purpose:**  
Traceroute (Linux) or Tracert (Windows) helps us see **the path** that data takes through the network.

**How it Works:**  
- It sends packets with a **Time To Live (TTL)** value that increases step by step.  
- Each router that handles the packet sends back a response.  
- This way, you can identify **where** the connection is breaking or slowing down.


## 3. **Telnet – Test Remote Port Connection**
**Purpose:**  
Telnet checks if a specific **port** on a remote device is open and responding.  
(Example: Port 80 for web server, 22 for SSH server)

**How it Works:**  
- You type something like `telnet 10.0.0.5 80`.  
- If the connection succeeds, that port/service is running.  
- If it fails, the service might be **down** or **blocked by firewall**.


## 4. **SSH – Secure Remote Access**
**Purpose:**  
SSH allows you to **securely log in** to another device (like a router, Linux server, or switch) over the network.

**How it Works:**  
- Uses **TCP Port 22**  
- Encrypts all data so it’s safe to use even on public networks.  
- Common for configuring network devices remotely.



## 🧾 **Tool Comparison Table**

| Tool | Purpose | Protocol | Secure | Common Port |
|------|----------|-----------|---------|--------------|
| **Ping** | Check basic network connectivity | ICMP | ❌ No | N/A |
| **Traceroute / Tracert** | Find the route packets take | ICMP / UDP | ❌ No | N/A |
| **Telnet** | Test or connect to remote ports | TCP | ❌ No | 23 |
| **SSH** | Secure remote login to a device | TCP | ✅ Yes | 22 |
