# VPNs and Tunneling Concepts

**VPN** - 

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

<img width="952" height="579" alt="Screenshot 2025-12-06 160301" src="https://github.com/user-attachments/assets/bcba80aa-6727-4b5a-a11a-44f1460d72a4" />


And this are the steps,  firstly-  both offices setup their vpn routers. They enter each other's public ippude so the devices know who they need to connect to. 
Second is after the setup, a secure tunnel formed between two offices. This tunnel is private, even though the connection is happening over the internet
Third is the vpn protects the tunnel using encryption and it checks that both sides are trusted. This keeps the connection safe
Now, when one office send data it goes through this protected tunnel, so no one else can see it
In the end, both offices can share their files, servers, and applications just like they are in the same building
