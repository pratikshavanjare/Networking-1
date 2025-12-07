# Firewall

A firewall is like a security guard for your network. It watches all the data trying to enter or leave your system and decides what should be allowed in and what should be blocked. It follows rules you set, so only safe and trusted traffic gets through. This helps protect your devices from hackers, viruses, and any unwanted access.

---

## Why Firewalls Are Important

• **Protect the network from hackers**

A firewall acts like your network’s bodyguard. It keeps an eye on all incoming connections and blocks anyone suspicious who tries to enter—just like stopping a stranger from walking into your house.

• **Block unauthorized access**

Sometimes people or programs try to access your system without permission. The firewall stops these unwanted guests automatically, ensuring only trusted users or devices can get inside.

• **Allow only safe communication**

Every piece of data trying to enter or leave the network is checked. The firewall makes sure that only clean, safe, and approved traffic is allowed, keeping everything running smoothly.

• **Prevent viruses and attacks**

Many cyberattacks start by sending harmful data into your system. A firewall helps block these threats before they reach your devices, reducing the chances of infections or damage.

• **Monitor network traffic**

A firewall keeps track of who is connecting, what they’re doing, and where the traffic is going. This helps detect unusual or risky behavior early and keeps the network secure.

---

## How a Firewall Works 

A firewall works just like a security guard standing at the gate of your network.
Every piece of data that tries to enter or leave is treated like a visitor at the gate.

1. **Checks every network packet** - 
    The firewall examines each packet one by one, making sure it knows exactly what type of data is coming in or going out.

2. **Compares it with firewall rules** - 
   It then checks the packet against a set of security rules—just like a guard checking a visitor list to see who’s allowed.

3. **Allows safe packets** - 
   If the packet matches the allowed list and looks safe, the firewall lets it pass through without delay.

4. **Blocks suspicious packets** - 
   If something looks risky, unknown, or violates the rules, the firewall immediately stops the packet to protect the network.

---

## Types of Firewalls

1. **Packet Filtering Firewall**

   - Acts like a basic gatekeeper that looks at the IP address, port number, and protocol of each packet.

   - Fast and simple, but only checks the header, so it can’t see deeper into the data.

2. **Stateful Firewall**

   - Remembers active connections, so it knows which packets belong to an ongoing session.

   - Safer than packet filtering because it can track traffic context, not just individual packets.

3. **Proxy Firewall**

   - Works like a middle-man between your network and the internet.

   - Hides the real IP addresses of your devices, making it harder for attackers to target your network.

4. **Next-Generation Firewall**

   - Goes beyond basic filtering, inspecting the content of packets deeply.

   - Can identify applications, block advanced threats, and stop malicious activity before it reaches your network. 

--------------------------------------------------------

# Router Redundancy (HSRP, VRRP, GLBP)

A network setup where multiple routers or paths ensure continuous connectivity if one router or link fails.

A router in a company like DXC Technology works just like an IT coordinator who handles all employee requests. When DXC employees open client websites, access internal tools, join Teams meetings, or download project files, all their requests go to the router first. The router decides the correct and fastest path—whether the data should go to a client server, DXC’s internal network, or the internet. It then brings the response back to the right employee’s laptop without mixing anything up. Just like an IT coordinator keeps work smooth and organized inside DXC, the router keeps all network traffic flowing safely and efficiently.

**Why we need routing?**

Without routing, devices would have no idea where to send information. Routing guides data by choosing the best, fastest, and correct path, just like Google Maps guides you on the road. It helps networks stay organized, avoids confusion, and makes communication smooth between different networks and locations.

**Here are three FHRP (First Hop Redundancy Protocols)**

1. HSRP
2. VRRP
3. GLBP

**1. HSRP (Hot Stand by Routing Protocol)** -  

HSRP is like having a backup router always ready, so your network never goes down.
Imagine DXC Technology is managing a client’s data center.
They use two edge routers for internet connectivity:

- **Router 1** – Active
- **Router 2** – Standby (HSRP backup)

Both routers share a virtual IP, which employees use as their default gateway.

If Router 1 suddenly goes down, HSRP immediately shifts traffic to Router 2.
Employees continue using applications, cloud services, and VPN without any downtime, and DXC maintains uninterrupted service for the client.

### Characteristics

1. **Redundancy –** Provides backup routers so if the primary fails, a standby takes over automatically.

2. **Virtual IP Address –** Routers share a single virtual IP that devices use as their gateway.

3. **Failover –** Automatic switch to standby router without interrupting network traffic.

4. **Active & Standby Roles –** One router is active (handles traffic), others are standby (wait to take over).

5. **Simple Configuration –** Easy to set up in small or large networks.

### How it works?

1. **Virtual IP Setup -** Multiple routers share a single virtual IP as the network’s gateway.

2. **Router Roles -**
Active Router: Handles all traffic.

3. **Standby Router -** Waits to take over if active fails.

4. **Hello Messages -** Routers send periodic “hello” packets to check the active router’s status.

5. **Failover -** If the active router fails, the standby router automatically becomes active.

6. **Seamless Traffic -** Devices continue using the same virtual IP, ensuring uninterrupted network access.

     <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/6db44d8a-839b-4871-96fd-e76662d275b5" />

---------------------------------------


**1. VRRP (Virtual Router Redundancy Protocol)** -  

VRRP is like having a backup driver ready to take over instantly if the main driver goes offline. In networking terms, it lets multiple routers work together so that if the main router stops working, another router can automatically take over without interrupting your network.

All devices in the network use a shared virtual IP address as their gateway.

This way, the network keeps running smoothly and without downtime, even if one router fails.

**Suppose -**
At DXC, employees connect to the virtual gateway 10.0.0.1.

Router R1 is the Master, handling all traffic.

Router R2 is the Backup, waiting silently.
If R1 fails, R2 instantly takes over, and employees continue working without noticing any problem.

### Characteristics

1. **Redundancy –** Provides backup routers so if the primary fails, a standby takes over automatically.

2. **Virtual IP Address –** Routers share a single virtual IP that devices use as their gateway.

3. **Failover –** Automatic switch to standby router without interrupting network traffic.

4. **Active & Standby Roles –** One router is active (handles traffic), others are standby (wait to take over).

5. **Simple Configuration –** Easy to set up in small or large networks.

### How it works?

1. **Virtual IP Address:** Multiple routers share a single virtual IP that all devices use as their gateway.

2. **Router Roles:**

-  **Master Router:** Handles all the network traffic.

-  **Backup Routers:** Standby routers monitor the master and wait to take over if needed.

3. **Heartbeat Messages:** Routers send regular “heartbeat” messages to check if the master is alive.

4. **Automatic Failover:** If the master stops responding, the highest-priority backup router automatically becomes the new master.

5. **Seamless Network:** Devices continue using the same virtual IP, so network access remains uninterrupted.

     <img width="450" height="450" alt="Screenshot 2025-12-07 095950" src="https://github.com/user-attachments/assets/93fc6c37-edcc-488a-85f5-360421f51955" />

---------------------------------------------------------------------------

**1. GLBP (Gateway Load Balancing Protocol)** -  

GLBP is like having multiple drivers sharing the same road, so traffic flows faster and no single driver is overloaded. In networking terms, it allows multiple routers to share a single virtual IP address while splitting traffic among them, instead of only one router handling everything.

- All devices use a shared virtual IP as their gateway.

- Unlike HSRP or VRRP, GLBP balances the traffic across multiple routers, improving performance and redundancy.

- If one router fails, the remaining routers take over the traffic, ensuring network continuity.

**Suppose -**

At DXC, employees’ systems use virtual gateway 10.0.0.1.

- Router R1 handles some users

- Router R2 handles others

- Router R3 handles the rest
  If R2 fails, R1 and R3 automatically take over its traffic, so everyone keeps working without interruption.

### Characteristics

1. **Redundancy –** Provides backup routers so if the primary fails, a standby takes over automatically.

2. **Virtual IP Address –** Routers share a single virtual IP that devices use as their gateway.

3. **Failover –** Automatic switch to standby router without interrupting network traffic.

4. **Active & Standby Roles –** One router is active (handles traffic), others are standby (wait to take over).

5. **Simple Configuration –** Easy to set up in small or large networks.

### How it works?

1. **Redundancy:** Multiple routers act as backups, so if one fails, others continue handling traffic.

2. **Load Balancing:** Distributes network traffic across all available routers instead of just one.

3. **Virtual IP Address:** All routers share a single virtual IP that devices use as their gateway.

4. **Active Virtual Gateway (AVG):** One router is elected as AVG to manage traffic distribution.

5. **Active Virtual Forwarders (AVFs):** Other routers forward traffic assigned by AVG.

6. **Automatic Failover:** If any router goes down, traffic is redistributed automatically without disrupting users.

7. **Seamless Network:** Users continue using the same gateway IP; no reconfiguration is needed.


<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/27f25b35-b861-4c0d-926e-72fd0ba0a23b" />

