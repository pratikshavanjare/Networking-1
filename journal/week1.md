#  Day 1

## Introduction to Networking

   Networking is basically about how computer and devices connect with each other to share data & resources.
   For example, when your laptop connects to wi-fi, it's part of a network that lets it talk to other devices and the internet.


### Types of Network
  There are 4 types of network which are below -

1. **PAN(Personal Area Network)** : Connects devices around one person, like mobile and laptop connectivity to earbuds.
2. **LAN(Local Area Network)** : Connects computers within a small area like home, school or all computer in office sharing a printer. 
3. **MAN(Metropoliton Area Network)** : Connects multiple LANs across a city or large campus.
4. **WAN(Wide Area Network)** : Connects networks across countries — like the Internet.


### Network Components

   There are two main types of components in networking:

### 1. Hardware Components

   These are the physical parts of a network, they help in connecting,sending and recieving data. like - Routers,Hub, Switches, Server, Firewall etc.

   **Hardware is further divided into:**
   - **End Devices** – These are the devices that people use to send or receive data. These are the source & destination points of communication. It is mainlyl used by users (like Computer, Laptop, Mobile)
   - **Intermediary Devices** – It Connects and control data, they make sure the data goes to the right place (like Router, Switch, Hub)
   - **Network Media** – This is the path that data uses to travel from one device to another. It can be wired (cables) or wireless (wi-fi signals)

### 2. Software Components

   These are the programs & rules that control how the network works. we can't touch but they make the network work. like - IP Addressing, Protocols (like TCP/IP) etc.


### Network Topologies

It shows that how computers and devices are connected to each other in a network.
There are 4 types of topologies -

1. **BUS Topology** - All computers or devices are connected to single cable, Simple but prone to failure. Example - Old Ethernet networks
   
   - **Pros** - We can modify and extend cable easily.
   
   - **Cons** - Until one device finishes sending data, others must wait. If two send together, their data can crash into each other.

      <img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/f8e891c6-6b1a-4d8c-93ca-b1ce8580d7d5" />


2. **RING Topology** - Devices will connect in a circle, Devices from a circular connection & data will travel in one direction. Example - Metro Networks.

    - **Pros** - data will sentin the form of Token.
 
    - **Cons** - If one fails or down or cannot send the message then whole network  will down.

      <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/f219d871-18c7-4776-9752-928b4b57a856" />


4. **STAR Topology** - All devices connect to one central device. Example - Most common in homes & Offices.

   - **Pros** - We can send data from any node to any other node in the network.

   - **Cons** - If central hub downs then whole  network will destroy.

       <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/8fff37ac-fed0-4885-8459-f0e537f95f95" />

   
4. **MESH Topology** - Every device is connected to every other device . so there will be multiple paths between devices. Example - Millitary communication Network.

   - **Pros** - It always establish a connection between two nodes (point to point connection).

   - **Cons** - It is difficult for installation & Configuration, It is expensive as well.

       <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/a98929b1-6db7-4fdb-91da-75a1c57d9065" />


### Importance of Networking in IT 

Networking is most important in the field of IT (Information Technology) because it helps devices & people connect, share, and communicate easily.
like -
   
   - **Resource Sharing** - Users can share files, printers, and internet without needing separate devices for everyone.
  
   - **Data Security** - It helps in protecting & monitoring data safely using firewalls and servers.
  
   - **Cloud Computing** - Networking gives access to the internet & cloud services like Google Drive, AWS or Azure.


#### Reference [Day 1](https://claude.ai/public/artifacts/e92959cb-3269-4546-b97d-e5dcd0aee458)

---------------------------------------------------------

# Day 2

We learnt Types of Networking(LAN, MAN & WAN) in detail -

1. **LAN** :
   - **Fullform** - Local Area Network
   - **Distance** - 1-2km
   - **Geographical Area** - Small area — like a home, school, or office.
   - **High-Speed** - Its speed is very high appx. (100mbps- 10gbps)
   - **Example** - Wi-Fi in our home, computers in a computer lab.
   - **Use** - It is used for connecting computers & devices in one buiding.
   - **Common Technologies** - LAN mostly uses Ethernet cables or Wi-Fi to connect nearby devices.

       <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/6d16549d-a607-46c0-b0f2-98c8890d4204" />


2. **MAN** :
   - **Fullform** - Metropoliton Area Network
   - **Distance** - 5-50km
   - **Geographical Area** - Medium area — like a city or large campus.
   - **High-Speed** - High (10mbps - 1gbps)
   - **Example** - City-wide Internet, college campus network.
   - **Use** - It is used for may LAN'S within one city.
   - **Common Technologies** - MAN uses high-speed fiber or wireless links to connect networks across a city.

       <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/a42f77eb-2529-409b-94e4-e5d81bfbf8ad" />


3. **WAN** :
   - **Fullform** - Wide Area Network
   - **Distance** - Unlimited
   - **Geographical Area** - Large area — across countries or the whole world.
   - **High-Speed** - It has lower or variable speed (1mbps - 100gbps)
   - **Example** - The Internet, bank branch networks.
   - **Use** - It is used for connecting many LAN's * MAN's together.
   - **Common Technologies** - WAN connects countries or continents using satellite or long-distance Internet lines.

       <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/adf563cd-d1c6-4664-adf3-1e6d3475438f" />


#### Let's Pratice with few questions -


**Scenario:** You are IT consultant for "EduTech Solutions" - an educational software company.

**Company Details:**
Main office: 100 employees in downtown building
Development center: 50 employees, 5 km away
Regional sales offices: 3 locations across the state
Remote workers: 25 employees working from home
Your Task:
Design a network architecture plan identifying:

What type of network for main office? (LAN/MAN/WAN) - **LAN**

How to connect development center? (LAN/MAN/WAN) - **MAN**

How to connect regional offices? (LAN/MAN/WAN) - **WAN**

How to support remote workers? (LAN/MAN/WAN) - **WAN**



#### Reference [Day 2](https://claude.ai/public/artifacts/f4b54e55-0e65-4185-8eb1-4ecbebbdf880)

----------------------------------

# Day 3

On Day 3 we learnt about Network Addresses that are IP Address and Mac Address.
Firstly will know, **What is Network Addresses?** -- A network address is like an identity for each device or it is like a name or address for a device in a networkn that helps computers find each other and share data easily. There are 2 Types of addresses that are below -


 1. **MAC Address**
    -  A MAC address is a unique ID number given to every device that connects to a network. like      a computer, phone, or printer. It is fixed and cannot be changed because it is built into the device when it is made.
    - It has 12 characters made of numbers and letters, usually written with colons - 00:1A:2B:3C:4D:5E
    - Its length has 48bits (6 bytes)
    

 2. **IP Address**
    - An IP Address is a unique number given to every device on a network, It helps devices find and talk to each other — like a home address helps people find your house.
    - There are 2 types of IP Address -
      1. IPv4: It has 32-bit address
         Example – 192.168.0.1
         It uses numbers with dots.

      3. IPv6: It has 128-bit address
         Example – 2001:0db8:85a3::7334
         It uses letters and numbers.

**How MAC & IP Addresses Work Together**

ARP is basically the way a computer figures out “I know the IP, but what is the MAC address?”
It helps one device talk to another on the same network.

**Step 1: Computer A wants to talk to Computer B**

Computer A decides to send some data to Computer B.
          * It already knows B’s IP address → 192.168.1.50
          * But it doesn’t know the MAC address linked to that IP
And without a MAC address, the actual data cannot be sent on a LAN. So, Computer A needs to ask the network, “Who owns this IP?”

**Step 2: ARP Broadcast – Asking the whole network**

Since Computer A has no idea who has that IP, it sends a broadcast message. Broadcast means everyone on the local network receives the message.

The broadcast message looks like this:
```
   Who has 192.168.1.50?
   Please tell me at MAC AA:BB:CC:DD:EE:FF
```
This is like Computer A shouting in a crowded room:
“Hey, who is 192.168.1.50? Please let me know so I can send you something!” Every device on the network hears it, but only the real owner responds.

**Step 3: Computer B hears the message and replies**

Computer B checks the broadcast and realizes:
“That’s my IP! They’re looking for me.”
So it sends a unicast reply directly back to Computer A:
```
   192.168.1.50 is at MAC 11:22:33:44:55:66
```
This reply tells Computer A exactly which MAC address belongs to the IP it’s trying to reach. Now, this is solved — Computer A knows both the IP and the MAC of Computer B.

**Step 4: Real data communication finally starts**

Now that the MAC address is known, Computer A can prepare a proper frame and send actual data.
A simplified version of the frame looks like this:
```
   Destination MAC: 11:22:33:44:55:66
   Destination IP: 192.168.1.50
```
From this moment onward, communication becomes smooth. The ARP process is done, and both devices can talk normally.


- **What is Packet Filtering?**
Packet filtering is a basic security method used in firewalls and routers. It checks every incoming or outgoing packet and decides whether to allow it or block it based on a set of rules.

- **How Packet Filtering Works**

Packet filtering is like a security guard for your network. Every piece of data comes in tiny packets. These packets have details like who sent it, where it’s going, and which door (port) it wants to enter.
The firewall looks at these details and decides:
“Is this safe? Should I let it in?”
“Is this unknown or risky? Then block it.”
So if a packet matches the rules you set (like allow port 80 or block port 22), it’s allowed to pass. If it doesn’t match any allowed rule, it gets stopped right there.

#### Reference [Day 3](https://claude.ai/public/artifacts/9933647d-a377-4e9e-9b69-e1e4030a2a55)
