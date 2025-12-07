# VPNs and Tunneling Concepts

## VPN

A VPN, or Virtual Private Network, is basically a secure connection over the internet. It allows safe communication between a device and a network. Companies use VPNs to protect their data and to give secure remote access to employees.

- A VPN encrypts the data, so no one else can read it.
- It also provides secure remote connectivity, which means employees can safely access company resources from anywhere.
- A VPN hides the user’s real IP address and ensures confidentiality and privacy.
- It is commonly used for site-to-site and remote-access connections.


**TYPES OF VPN** -

**1. Remote Access VPN**
     - This VPN is used by single users.
     - For example, if an employee is working from home, they can connect to the office network safely using this VPN.

**2. Site-to-Site VPN**
     - This is used to connect two office locations.
     - Like if a company has one office in City A and another in City B, this VPN connects both offices securely.

**3. Client-to-Site VPN**
     - Here, a user’s device, like a laptop or phone, connects to the company network using VPN software.
     - It is mostly used for remote workers.

**4. Site-to-Client VPN**
     - In this type, the company’s network gives access to a user at another location.
     - It’s almost like remote access but used for specific sites.

**5. SSL VPN**
     - This VPN works through a normal web browser.
     - You don’t need to install any software — just open the website and log in securely.

**6. IPsec VPN**
     - IPsec is a strong security protocol.
     - It protects data and is used for both remote access and connecting two offices.

**7. PPTP / L2TP VPN**
     - These are older VPN types.
     - They are easy to set up but PPTP is less secure.
     - L2TP is better when used with IPsec.

**8. MPLS VPN**
     - This is used by big companies.
     - It provides a fast and private connection between many office branches.
     - It is reliable but costly.


**VPN Uses in Corporate World**

So, for corporate real world example I am taking second type of VPN that is site to site connection, Here..... I will connect two offices from different cities and will see how VPNs in corporate world help companies connect different offices securely. Like a secure tunnel, it lets them share files, servers, and apps safely without needing expensive physical connections.

   <img width="700" height="650" alt="Screenshot 2025-12-06 160301" src="https://github.com/user-attachments/assets/bcba80aa-6727-4b5a-a11a-44f1460d72a4" />

<br>

And this are the steps,  firstly-  both offices setup their vpn routers. They enter each other's public ip so the devices know who they need to connect to. 
Second is after the setup, a secure tunnel formed between two offices. This tunnel is private, even though the connection is happening over the internet
Third is the vpn protects the tunnel using encryption and it checks that both sides are trusted. This keeps the connection safe
Now, when one office send data it goes through this protected tunnel, so no one else can see it.
In the end, both offices can share their files, servers, and applications just like they are in the same building.

------------------------------------------------------------------------------------------


## Tunneling

Tunneling is a method of sending data across a network that may not support the original protocol by wrapping the data inside a supported protocol.

Think of it like this: You want to send a letter (your original data), so you put it in an envelope (encapsulation), and then put the envelope in a package (outer protocol) for shipping. At the destination, the package is opened, then the envelope, and finally the letter is read.

**How Tunneling Works**

1. **Encapsulation:** Original data packet is wrapped with a tunnel header, sometimes encrypted.

2. **Transport:** Encapsulated packet travels securely through the network.

3. **Decapsulation:** At the destination, the tunnel header is removed, and the original data is delivered.


**Types of Tunneling**

**1. PPTP (Point-to-Point Tunneling Protocol)**

  - Works at Layer 2 (Data Link) and uses TCP 1723.

  - Pros: Very easy to set up, fast, comes built into many operating systems.

  - Cons: Old, weak security, vulnerable to attacks.
    

**2. GRE (Generic Routing Encapsulation)**

  - Works at Layer 3 (Network).

  - Pros: Lightweight, supports multicast, simple to use.

  - Cons: No encryption by default, usually combined with IPSec for security.

  - Use Case: Often used for site-to-site VPNs.

**3. L2TP (Layer 2 Tunneling Protocol)**

  - Works at Layer 2 (Data Link), uses UDP 1701.

  - Pros: Secure when combined with IPSec, widely supported.

  - Cons: Double encapsulation makes it slightly slower.

  - Use Case: L2TP/IPSec VPN for secure connections.

**4. SSH Tunneling**

  - Works at Layer 7 (Application), uses TCP 22.

  - Pros: Very secure, encrypted, flexible for port forwarding.

  - Cons: Limited protocol support, not a full VPN.

  - Use Case: Secure remote access or forwarding specific ports.

    <img width="700" height="650" alt="image" src="https://github.com/user-attachments/assets/ea760a71-db54-4050-99a9-f010f113aef8" />




<br>

### Difference between VPN & Tunneling


| Feature        | VPN                                                                                        | Tunneling                                                            |
| -------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| **Definition** | Complete solution for secure network access; encrypts, authenticates, and protects traffic | Method of sending data across networks by encapsulating it           |
| **Scope**      | Broad: includes encryption, authentication, and secure access                              | Specific: only encapsulates data for transport                       |
| **Security**   | End-to-end encryption and authentication ensure safety and privacy                         | Depends on protocol; may or may not be encrypted                     |
| **Purpose**    | Creates a secure private network over the internet                                         | Allows data to travel across networks that don’t normally support it |
| **Components** | Combines tunneling, encryption, and authentication                                         | Only encapsulation, no extra security unless added                   |
| **Analogy**    | An armored vehicle traveling on a highway                                                  | The highway itself that carries the vehicle                          |


#### Reference [Day 1](https://claude.ai/public/artifacts/a40f8498-55f3-4a59-aa79-6ec64d843462)
