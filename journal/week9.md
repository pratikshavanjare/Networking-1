# Subnetting & CIDR


## What is Subnetting?
Dividing a large block of networks into smaller parts. and we are doing subneeting to reduce the ip add wastage. 
Let's take an example, There are two computers with ip address 1.1.1.1 & 1.2.1.1 respectively. They can communicate because , In class C first bits should be same. So, it will communicate but if IPs will be different like 1.1.1.1 want to communicate 7.2.1.1 it will can't. So,for that it will need reouter for communicating different networks.

**Let's do simple question step by step---**

Ware taking example of class C. Subnetting will complete in 6 steps...
Suppose, we want to connect 100 PCs via 4 switches . so, there will be 100ips will be used and rest of 156 ips will be waste. so, thatit will reduce the wastage of ip address. 

1. **Required Host** -
   Total no. of PCs are 100
   so, we need only 2^7=128
   that means, Host = 7
   
2. **Converted Network bits = Total host bits - Required host bits** -
   Total host bits are 8 & Required host bits are 7. so,
   8-7 = 1(Network bit)

3. **Total Network bits = Total Network bits + Converted Network bits** -
   Total network bits will be 24 because in class there will be 3 octacts & each octet has 8 bits.so, 8+8+8 =24
   & we had already Converted Network bits is 1. so,
   24 + 1 = /25

4. **Subnets** -
   2^n = 2^1 = 2 (Here n is network bits)

5. **Blocksize** -
   2^H = 2^7 = 128 (Here H is host)

6. **Range** -
   Main IP add is 192.168.1.0 . So, here it will divide it into 2 subnets, that will be -
   192.168.1.1/25(Network ID) & 192.168.1.127/25(Broadcast ID)



## Why We Use Subnetting

| Reason | Simple Meaning |
|--------|----------------|
|  Organize the network | Easier to handle small networks |
|  Better performance | Less traffic and faster connection |
|  More security | Each subnet can be protected separately |
|  Save IP addresses | Avoid wasting IPs |

---

## How an IP Address Works
Every IP address has two parts:

Network Part + Host Part

- **Network Part** → tells which network the device belongs to  
- **Host Part** → tells which specific device inside that network  

Example:  
`192.168.1.10` → IP Address 
`192.168.1` = network part  
`10` = host part

---

## Subnet Mask

The **subnet mask** shows how many bits are for network and how many for host.

| Subnet Mask | CIDR | Total IPs | Usable IPs |
|--------------|------|------------|-------------|
| 255.255.255.0 | /24 | 256 | 254 |
| 255.255.255.128 | /25 | 128 | 126 |
| 255.255.255.192 | /26 | 64 | 62 |
| 255.255.255.224 | /27 | 32 | 30 |

We lose 2 IPs each time — one for **Network** and one for **Broadcast**.

---

## Meaning of Addresses

| Type | Example | Meaning |
|------|----------|----------|
| **Network Address** | 192.168.1.0 | Name of subnet |
| **First Host** | 192.168.1.1 | First usable IP |
| **Last Host** | 192.168.1.62 | Last usable IP |
| **Broadcast** | 192.168.1.63 | Used to send data to all devices |

 Note: Network and Broadcast addresses cannot be used for devices.

---

## Simple Formulas

| What You Want | Formula | Example |
|----------------|----------|----------|
| Number of Subnets | 2ⁿ | n = bits borrowed (2 bits → 4 subnets) |
| Hosts per Subnet | 2ʰ - 2 | h = bits left for host |
| Subnet Increment | 256 - last octet value | 256 - 192 = 64 |

   <img width="900" height="500" alt="Screenshot 2025-12-06 205631" src="https://github.com/user-attachments/assets/59208540-547e-4fae-9e5f-90bfd170d0c8" />


---





# CIDR (Classless Inter-Domain Routing) – 

---

## What is CIDR?

**CIDR** stands for **Classless Inter-Domain Routing**. It’s a way to **write and manage IP addresses more efficiently**.
Before CIDR, networks were divided into fixed classes (A, B, C).  
But this wasted many IP addresses.

So CIDR was created to **break free from fixed classes** and allow **flexible subnetting**.

---

1. **No Classless** - It means IP addresses don’t follow old A/B/C classes (like Class A = /8, Class B = /16, etc). Instead, we use slash notation (/something) to show how many bits are used for the network part.
2. **Only Blocks** - It has only blocks like, total bits are 32 in which 28(Block ID) & 4(Host ID) and if we want to calculate hosts so that will be, 2^4 = 16 Hosts.
3. **Notation(n)** - Its a mask or number of bits represent block or network. like -
   200.10.20.40/28 this is an IP Address with subnet mask will be 255.255.255.240 (here 28 is mask, so if we convert 28 to binary number ,we will get 240).
   Now, will calculate the Network ID, Converting last octet to binary 200.10.20.40/28 to 20.10.20.0010 1000 then except 4 will do 0, 200.10.20.0010 0000 , then      will get Network ID 200.10.20.32/28.

   Another Method is -
   255.255.255.240
   200.10.20.40
   ---------------
   255.10.20.32/28 (will get Network ID after dividing this)

## Rules of CIDR -
1. Address should be contigous like, 200.10.20.32, 200.10.20.33, 200.10.20.34..........
2. Number of Addresses in a block must be in power of 2.
3. First address of every block must be evenly divisible with size of block.

## Example of CIDR Notation

A CIDR address looks like this:


Here:
- `192.168.1.0` → network address  
- `/24` → means **24 bits are used for the network part**

So, `/24` = 255.255.255.0 (subnet mask)

---

## How CIDR Works

CIDR shows how many bits in the IP address are used for the **network** part.  
The remaining bits are for the **host** part (devices).

Example:  
| CIDR | Binary Network Bits | Subnet Mask | Total IPs | Usable IPs |
|------|----------------------|--------------|-------------|-------------|
| /24 | 11111111.11111111.11111111.00000000 | 255.255.255.0 | 256 | 254 |
| /25 | 11111111.11111111.11111111.10000000 | 255.255.255.128 | 128 | 126 |
| /26 | 11111111.11111111.11111111.11000000 | 255.255.255.192 | 64 | 62 |
| /27 | 11111111.11111111.11111111.11100000 | 255.255.255.224 | 32 | 30 |
| /28 | 11111111.11111111.11111111.11110000 | 255.255.255.240 | 16 | 14 |

---

## CIDR and Subnetting

CIDR and Subnetting work **together**.  
When we subnet a network, we use CIDR notation to **show how many bits are used for the network**.

For example:  
- `192.168.1.0/24` → one big network  
- `192.168.1.0/26` → smaller subnet (part of /24 network)

So `/26` means:
- 26 bits → for network  
- 6 bits → for host  
- Subnet mask = 255.255.255.192

---
