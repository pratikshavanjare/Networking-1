## DAY 18

# Network Troubleshooting Tools

When the network doesn’t work properly, we use some basic tools to **check where the problem is** — whether it’s with the connection, the path, or the remote system.  
Here are the four most common tools used for troubleshooting.

---

## 1. **Ping – Test Connectivity**

Ping is one of the simplest yet most powerful tools used in networking to check whether two devices can communicate with each other. You can think of it as the digital version of shouting “Hello! Can you hear me?” across a room and waiting to see if someone responds. If they reply, you know the path between you and them is clear. If they don’t reply, then something along the way is blocking the communication.

**Purpose:**  

The main purpose of ping is to confirm whether a device on the network is alive, reachable, and working. By using ping, you can quickly find out:

- If your laptop can reach your router
- If your router can reach the internet
- If your internet can reach a website
- If a server or device is responding normally

**It helps identify whether the problem is with:**

- Your device
- The network connection
- The destination device
- Or the path between them

**How it Works:**  

When you use the ping command, your computer uses a protocol called ICMP (Internet Control Message Protocol) to send a small “test message” to another device. These test messages are known as ICMP Echo Requests.

**Step-by-step explanation of what happens during a ping:**

**1. Your device creates a tiny packet**
This packet contains:
- A sequence number
- A timestamp
- Source and destination information

**2. The packet is sent to the target device**
     This could be a router, server, website, or another computer.

**3.If the target is reachable, it will send back a reply called an ICMP Echo Reply.**
**4. Your device receives the reply and measures:**
- How long the packet took to go and come back (Round Trip Time)
- Whether any packets were lost
- How many replies were successful

This helps you understand if the network is healthy or if there is a failure somewhere.

**Why It’s Useful:**

- If your internet is working
- If a device is online
- If the path is slow or unstable
- Where a network issue might be happening

**Ping Command**
```
ping 192.168.1.1
ping google.com
```
  
----------------------------------------------------------------------------


## 2. **Traceroute / Tracert – Trace the Path**

Traceroute is a tool that shows the exact path your data takes from your device to a destination (like google.com).
It doesn’t just tell you whether the destination is reachable — it shows every stop in between, step by step.

**Purpose:**  
Traceroute (on Linux) and Tracert (on Windows) are tools that help you actually see the journey your data takes across a network.
Whenever you open a website, send a message, or access a server, your data does not travel in one straight line. Instead, it passes through many routers and networking devices along the way—almost like taking a bus that stops at multiple stations before reaching the final destination.

Traceroute shows you every one of those stations (called hops) and gives you a complete map of its path.

**How it Works:** 

When you run a traceroute command, your computer sends special packets toward the destination. But instead of sending them normally, it plays a smart trick using something called TTL (Time To Live).

Think of TTL like a countdown timer attached to each packet. It tells the packet how many “hops” it is allowed to travel before it expires.

**Here’s how traceroute uses TTL step by step:**

**Step 1: Start with TTL = 1**
- Your computer sends the first packet with a TTL of 1.
- The moment it reaches the first router, the TTL becomes 0 and expires.
- Since the packet expired, the first router sends a message back:
  “Hey, I’m hop 1, and your packet died here.”
- That is how we learn the identity and response time of the first router.

**Step 2: Send another packet with TTL = 2**
- This packet survives the first hop…
- But it expires at the second router.
- So the second router also sends back a message identifying itself.

**Step 3: Increase TTL for each packet**

Traceroute keeps increasing the TTL (3, 4, 5, etc.).
Each packet travels one hop further before expiring.

By doing this continuously, traceroute gathers information about every router along the path until it finally reaches the destination.

This step-by-step method builds a complete list:
- Hop 1
- Hop 2
- Hop 3 …and so on

This continues until the destination sends back the final reply indicating:
“Yes, your packet reached me. The journey is complete.”

**Why Traceroute Is So Important**

Traceroute is important because it tells you exactly where your network problem is happening. Instead of guessing, it shows the point where your data gets stuck or slows down.

- **If the issue is at hop 1 or 2** → the problem is inside your home or office network.

- **If the issue appears in the middle hops** → your internet provider (ISP) might be facing a routing problem.

- **If the problem happens near the last hops** → the issue is likely on the server side.

- **If one hop has very high delay** → that router is overloaded, slow, or far away.

**Tracert Command**
```
tracert 192.168.1.1
tracert google.com
```

-------------------------------------------------------------------------

## 3. **Telnet – Test Remote Port Connection**

Telnet helps you check whether a specific service on another device is running or not.
It’s like testing if a certain door is open — if you can enter, the service is active; if the door is locked, something is blocking or the service is not running.

**Purpose:**  

Telnet is used to check whether a particular port on a remote device is open and responding.
Every service runs on a specific port — for example:

- Port 80 → Website (HTTP)
- Port 22 → SSH remote login
- Port 25 → Email server (SMTP)

With Telnet, you can test if these services are actually reachable.
It’s like trying to open a specific door in a building to see if it’s unlocked and someone is inside.

**How it Works:**  

Telnet tries to connect your computer to a specific port on another device.
When you run a command like:
```
    telnet 192.168.1.10 80
```

your computer checks if port 80 on that device is open.

- If the port is open, Telnet connects and lets you communicate directly with that service.

- If the port is closed or blocked, the connection fails.

**Why Telnet Is So Important**

Telnet is important because it helps you check whether a specific device and a specific port are open and responding.
While tools like ping check basic connectivity, Telnet goes deeper and tells you if a service is actually working.

- **If Telnet connects successfully** → the device is reachable and the port/service is running.

- **If Telnet fails to connect** → the port may be closed, blocked by a firewall, or the service might be down.

- **If some ports work and others don’t** → you know exactly which service is having issues.

- **If the device doesn’t respond at all** → there may be a network or configuration problem.

**Telnet Command**
```
telnet 192.168.1.1
telnet google.com
```

----------------------------------------------------------------

## 4. **SSH – Secure Remote Access**

SSH is a secure method that lets you log in and control another computer or network device remotely. It protects your connection by encrypting everything you send or receive.

**Purpose:**  

The main purpose of SSH is to allow safe remote access.
Admins use it to:

- Configure routers, switches, and servers
- Transfer files securely
- Manage devices from anywhere without being physically present

Basically, it gives you a safe doorway to another system.

**How it Works:**  

SSH works by creating a private, encrypted tunnel over the network.
Here’s the simple flow:

1. You try to connect to a device using SSH (usually on Port 22).

2. Your computer and the remote device authenticate each other, so you know you’re connecting to the right machine.

3. They exchange encryption keys and set up a secure session.

4. After that, anything you type—passwords, commands, data—travels through an encrypted channel, so no one else can read it.

**Why It’s Important:**

SSH is important because it gives you security + convenience at the same time.

- Your login details stay safe
- Hackers cannot see what commands you run
- You can manage devices from anywhere in the world
- It protects sensitive network operations
- It replaces old, unsafe methods like Telnet

**SSH Command**
```
ssh -l username 8.8.8.8
Password: cisco123
```

-------------------------------------------------------------------------

## **Tool Comparison Table**

| Tool | Purpose | Protocol | Secure | Common Port |
|------|----------|-----------|---------|--------------|
| **Ping** | Check basic network connectivity | ICMP | No | N/A |
| **Traceroute / Tracert** | Find the route packets take | ICMP / UDP | No | N/A |
| **Telnet** | Test or connect to remote ports | TCP | No | 23 |
| **SSH** | Secure remote login to a device | TCP | Yes | 22 |


#### Reference [Day 1](https://claude.ai/public/artifacts/f62c7089-2ba4-41ec-ac60-2d38a54a65d9)

