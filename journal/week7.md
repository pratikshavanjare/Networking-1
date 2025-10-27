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

#### Standard ACL - 
It is used to allow or block traffic based only on the source IP address. It is simpler but less flexible than extended ACL. 

##### Characteristics
- It checks where data is coming from.
- Number range : 1-99 and 1300-1999.
- It always usually placed near to the destination.
- It is used only when you want to block or allow entire network.

#### Extended ACL
It will do the same thing controlling network traffic but more precisely. It will use source IP as well as Destination IP, protocol and port number for filtering traffic.

##### Characteristics
- Number Range : 100-199 and 2000-2699.
- It is more complex amd detailed traffic control.
- It always usually placed near to the Source.
- It is used only when you want to block or allow specific protocol or port on a network.

![ACL Lab](https://github.com/pratikshavanjare/Networking-1/blob/e821357ac79eb612a96d09e526e8a329e98601eb/Media/DHCP%20Image.png)
#### Reference [Day 15]([https://claude.ai/public/artifacts/cab20ca6-7445-4439-880e-78db376be78c](https://claude.ai/public/artifacts/bd93a197-c4e7-4055-8fb8-244f36c6d823))
