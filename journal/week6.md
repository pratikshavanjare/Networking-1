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
1. DHCP Server - It holds the IP Address and give them out to clients.
2. DHCP Client - Any device (PC, Phone, Printer) that requests an IP address from DHCP server.
3. IP Address Pool - A range of IP addresses that the DHCP server can assign, ensures there are enough IP Addresses for all devices and prevents conflicts from duplicate IPs.
4. Lease - The amount of time a client can use the assigned IP addess and after lease expires ip address return to the pool.

### DHCP Process (DORA) 
Its a four step process to assign IP adresses---
1. DISCOVER - The client sends a DHCP Discover message to find available DHCP servers.
2. OFFER - The DHCP server replies with a DHCP Offer, giving an available IP address and network info.
3. REQUEST - The client responds with a DHCP Request, asking to use the offered IP.
4. ACKNOWLEDGE - The DHCP server sends a DHCP Acknowledgement, confirming the IP assignment.

### Port numbers used by DHCP
- UDP Port 67 (used by DHCP Servers)
- UDP Port 68 (used by DHCP Clients)

### Methods of IP Address Assignment
Now we will see how IP Adress assigns for differentallocation
1. Dynamic Allocation - The DHCP server assigns an IP address to a client temporarily from its pool.
2. Automatic Allocation - The DHCP server assigns an IP address to a client permanently (same IP every time).
3. Static Allocation - The DHCP server always gives the same IP to a specific device, based on its MAC address.
   (Note - Dynamic allocation is the most used method as it efficiently manages IP address resources)

### LEASE Management 
Now will see what is DHCP Lease management, renewal process and its benefits-
When a DHCP server assigns an IP address to a client, it’s not permanent—it’s given for a fixed time called a lease.

LEASE RENEWAL PROCESS-
1. T1 Timer (50% of lease) - when half of the lease time has passed then theclient automatically asks theserver to renew itsIP lease.
2. T2 Timer (87.5% of lease) - If server didn't response or renewal fails, the client tries again and broadcast a renewal request to any DHCP server.
3. Lease Expiration - When the lease time completely runs out and if client didn't renew, it will stop using that IP and request a new one from DHCP server.

BENEFITS - It is efficient to reuse and flexible for mobile devices.

### DHCP Lab Image(https://github.com/pratikshavanjare/Networking-1/blob/e821357ac79eb612a96d09e526e8a329e98601eb/Media/DHCP%20Image.png)

### Reference [Day 13](https://claude.ai/public/artifacts/cab20ca6-7445-4439-880e-78db376be78c)


-----------

## NTP Protocol
NTP stands for Network Time Protocol. It is used for accurate time or make sure all computers and devices on a network have the same correct time.


## NAT & PAT

### What is NAT?
NAT is stands for Network Address Tranlation, It translates IP Address from public IP to private IP or private IP to public IP.
let's understand with example, Suppose we are working in a company and wants to access some data from server which is belongs to outside so the request will go in the form of data packets which has its own IP address, as company has its own router so here NAT comesit will change private IP to public IP and after getting information form server it will come again to router and will change public IP to private IP.

And the purpose of NAT is to allows multiple devices on a private network to share single public IP address, it uses IPV4, provides security by hiding internal IP address.

### Types of NAT
There are 3 types of NAT suh as -
1. Static NAT - 
2. Dynamic NAT - 
3. PAT(Port Address Translation) - 

