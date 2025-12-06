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

1. **Checks every network packet**
The firewall examines each packet one by one, making sure it knows exactly what type of data is coming in or going out.

2. **Compares it with firewall rules**
It then checks the packet against a set of security rules—just like a guard checking a visitor list to see who’s allowed.

3. **Allows safe packets**
If the packet matches the allowed list and looks safe, the firewall lets it pass through without delay.

4. **Blocks suspicious packets**
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

---
