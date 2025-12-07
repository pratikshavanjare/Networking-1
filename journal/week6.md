# DHCP Protocol 

## What is DHCP Protocol?
Let's learn with example, Suppose there is one network in our Host and we want to share our data to that host or that host wants to send data somewhere, if network is small and number of host is only one so we can configure IP Address manually but what if large networks and number of hosts will be increases we can't do it manually, So here DHCP Protocol comes -
           "It stands for Dynamic Host Configuration protocol. It is used to configure IP Addresses dynamically to the hosts or devices with lease time."
This protocol matters a lot because it automates IP address assignment process, reduces admins overhead etc.

DHCP contents Table which has DUAL nature -
Dual nature in the sense It has static and Dynamic both, They are as below 
| Device Name | IP Address   |
|--------------|--------------|
| Laptop     | 10.0.0.1  |      } Static 
| Mobile    | 10.0.0.2  | 
| PC    | 10.0.0.3 | 

| Device Name | IP Address   | Lease Time   |
|--------------|--------------|-------------|
| Laptop     | 10.0.0.1  | 10 min     |      } Dynamic 
| Mobile    | 10.0.0.2  | 20 min |
| PC         | 10.0.0.3 | 5 min    |

So, here in static if host will ask IP Address we configure to it but in dynamic it will only assigns IP when host will send request to the pool(A pool is a collection of all available IP addresses that can be assigned to devices in a network)so it can give to the particular host otherwise it will not. 

### DHCP Components

Now will see how it mananges network automatic, efficient and error free -
1. **DHCP Server -** It holds the IP Address and give them out to clients.
2. **DHCP Client -** Any device (PC, Phone, Printer) that requests an IP address from DHCP server.
3. **IP Address Pool -** A range of IP addresses that the DHCP server can assign, ensures there are enough IP Addresses for all devices and prevents conflicts from duplicate IPs.
4. **Lease -** The amount of time a client can use the assigned IP addess and after lease expires ip address return to the pool.

### DHCP Process (DORA) 

Its a four step process to assign IP adresses---
1. **DISCOVER -** The client sends a DHCP Discover message to find available DHCP servers.
2. **OFFER -** The DHCP server replies with a DHCP Offer, giving an available IP address and network info.
3. **REQUEST -** The client responds with a DHCP Request, asking to use the offered IP.
4. **ACKNOWLEDGE -** The DHCP server sends a DHCP Acknowledgement, confirming the IP assignment.

### Port numbers used by DHCP

- UDP Port 67 (used by DHCP Servers)
- UDP Port 68 (used by DHCP Clients)

### Methods of IP Address Assignment

Now we will see how IP Adress assigns for differentallocation
1. **Dynamic Allocation -** The DHCP server assigns an IP address to a client temporarily from its pool.
2. **Automatic Allocation -** The DHCP server assigns an IP address to a client permanently (same IP every time).
3. **Static Allocation -** The DHCP server always gives the same IP to a specific device, based on its MAC address.
   (Note - Dynamic allocation is the most used method as it efficiently manages IP address resources)

### LEASE Management 
Now will see what is DHCP Lease management, renewal process and its benefits-
When a DHCP server assigns an IP address to a client, it’s not permanent—it’s given for a fixed time called a lease.

LEASE RENEWAL PROCESS-
1. **T1 Timer (50% of lease) -** when half of the lease time has passed then theclient automatically asks theserver to renew itsIP lease.
2. **T2 Timer (87.5% of lease) -** If server didn't response or renewal fails, the client tries again and broadcast a renewal request to any DHCP server.
3. **Lease Expiration -** When the lease time completely runs out and if client didn't renew, it will stop using that IP and request a new one from DHCP server.

**BENEFITS -** It is efficient to reuse and flexible for mobile devices.

![DHCP Lab](https://github.com/pratikshavanjare/Networking-1/blob/e821357ac79eb612a96d09e526e8a329e98601eb/Media/DHCP%20Image.png)
#### Reference [Day 1](https://claude.ai/public/artifacts/cab20ca6-7445-4439-880e-78db376be78c)


-----------

###(Advance Tpoics)

## NTP Protocol
NTP stands for Network Time Protocol. It is used for accurate time or make sure all computers and devices on a network have the same correct time.
Its is essential because it makes sure secure coonections (like HTTPS/FTP etc) work properly, it keeps device's time accurate.

### How it works??
The working is done by 3 steps, they are below -
1. The PC will ask to the time server - "What's the time"?
2. The server will reply with the correct time.
3. And then that computer adjusts its clock as on that time.

![NTP](https://github.com/pratikshavanjare/Networking-1/blob/e3e69d028d768c589d70ae11172e018cd2f72d73/Media/NTP%20Image.png)
------------
## 3 Way Handshake Protocol

It is mainly used in TCP(Transmission Control Protocol) to establish a connection between two devices (like Laptop, Computer etc).

#### This process will done in 3 steps that is-

1. **SYN -** Client says - "Hello, I want to establish a connection".
2. **SYN-ACK -** then Server replies - " Okay, let's start".
3. **ACK -** then Client confirms - "Great, let's start communicating!".
After these 2 steps connection will established and th devices will start communticating or can sent data safely.

![3 way Handshake](https://github.com/pratikshavanjare/Networking-1/blob/d5c264eb3e5f6d03cb930886cdffffa2809c887c/Media/3wayhandshake.png)
-----------------

## NAT & PAT

### What is NAT?
NAT is stands for Network Address Tranlation, It translates IP Address from public IP to private IP or private IP to public IP.
let's understand with example, Suppose we are working in a company and wants to access some data from server which is belongs to outside so the request will go in the form of data packets which has its own IP address, as company has its own router so here NAT comes it will change private IP to public IP and after getting information form server it will come again to router and will change public IP to private IP.

And the purpose of NAT is to allows multiple devices on a private network to share single public IP address, it uses IPV4, provides security by hiding internal IP address.

### Types of NAT
There are 3 types of NAT suh as -
1. **Static NAT** - one-to-one maping between private & public ip addresses means maps one private IP to one public IP permanently.
2. **Dynamic NAT** - Maps a private IP to any available public IP from a pool.
3. **PAT(Port Address Translation)** - It maps multiple private ip addresses to single public ip using port numbers.

### What is PAT?
PAT is stands for Port Address Translation. It is the advance version of NAT that allows many devices to share a single public IP address by using different pport numbers to identify each connection.
Benifits of PAT are it allows many devices for sharing one public IP address, cost effective & stand implementation in routers.

## Use Cases in Corporate Networks

1. **Internet Access for Employees** - PAT allows a lot of employees to access internet using pool of IP addresses.
2. **Server Publishing** - Internal servers are accessible from the internet while keeping them on the internal network.
3. **Security Enhancement** - It is unable to hack by attakers dut to hiding internal IP addressed.
4. **Cloud Service Access** - By using NAT, Organizations provide controlled access to cloud resources while maintaining internal network segmentation.
5. **Testing & Developemnt** - They canuse to simulate production networks with different addressing schemes.
   
![NAT-PAT](https://github.com/pratikshavanjare/Networking-1/blob/cf507db41f7a88f30f5c7480aaa046deac9bd80e/Media/NAT-PAT.png)
#### Reference [Day 2](https://claude.ai/public/artifacts/553de791-6828-4740-becf-0fb4af7e53b7)
