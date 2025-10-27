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

 **Key Point:**  
ACLs are applied to a router’s **interface**, either **inbound** or **outbound** direction.

---

###  Example
Suppose, we want to block on device from accessing our network for that we can use ACL rule to deny that IP and allow others.
So, only traffic from allowed IPs will pass through the router interface.

---

###  Types of ACL
There are two types of ACL -
1. Standard ACL
2. Extended ACL

#### Standard ACL - 
