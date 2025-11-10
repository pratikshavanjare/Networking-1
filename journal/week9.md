## DAY 18

# Subnetting & CIDR
---

## What is Subnetting?

Subnetting means dividing one **big network** into **small networks** called **subnets**. It’s just like dividing one big classroom into small groups so it’s easier to manage and control.

For example:  
If we have a big network of 192.168.1.0, we can break it into smaller parts so each department or group gets its own mini network.
---

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
`192.168.1.10` →  
`192.168.1` = network part  
`10` = host part

---

## Subnet Mask (Simple View)

The **subnet mask** shows how many bits are for network and how many for host.

| Subnet Mask | CIDR | Total IPs | Usable IPs |
|--------------|------|------------|-------------|
| 255.255.255.0 | /24 | 256 | 254 |
| 255.255.255.128 | /25 | 128 | 126 |
| 255.255.255.192 | /26 | 64 | 62 |
| 255.255.255.224 | /27 | 32 | 30 |

We lose 2 IPs each time — one for **Network** and one for **Broadcast**.

---

## Example: Dividing a Network

We have a big network:  
**192.168.1.0/24** → 256 IPs (from 192.168.1.0 to 192.168.1.255)

We want to make **4 small networks**.

### Step 1: Find bits to borrow  
We need 4 subnets → 2² = 4 → so we borrow **2 bits**.

### Step 2: New subnet mask  
Old = /24  
New = /26 → Subnet Mask = **255.255.255.192**

### Step 3: Subnets created

| Subnet | Network Address | Usable IPs | Broadcast |
|--------|------------------|-------------|------------|
| 1 | 192.168.1.0 | 192.168.1.1 – 192.168.1.62 | 192.168.1.63 |
| 2 | 192.168.1.64 | 192.168.1.65 – 192.168.1.126 | 192.168.1.127 |
| 3 | 192.168.1.128 | 192.168.1.129 – 192.168.1.190 | 192.168.1.191 |
| 4 | 192.168.1.192 | 192.168.1.193 – 192.168.1.254 | 192.168.1.255 |

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

---

## Real-Life Example

Let’s say a company has 4 departments:
- HR  
- IT  
- Sales  
- Finance  

You don’t want them all on the same network.  
So, you create 4 subnets from 192.168.1.0/24:

| Department | Subnet | IP Range | Devices |
|-------------|---------|-----------|----------|
| HR | 192.168.1.0/26 | 192.168.1.1 – 62 | 60 |
| IT | 192.168.1.64/26 | 192.168.1.65 – 126 | 60 |
| Sales | 192.168.1.128/26 | 192.168.1.129 – 190 | 60 |
| Finance | 192.168.1.192/26 | 192.168.1.193 – 254 | 60 |

Now each department has its own small network.  
This makes the network faster, safer, and easier to manage.

---
---------------------------------------------------------


# CIDR (Classless Inter-Domain Routing) – Simple Explanation

---

## What is CIDR?

**CIDR** stands for **Classless Inter-Domain Routing**.  
It’s a way to **write and manage IP addresses more efficiently**.

Before CIDR, networks were divided into fixed classes (A, B, C).  
But this wasted many IP addresses.

So CIDR was created to **break free from fixed classes** and allow **flexible subnetting**.

---

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

## Example: Difference Between /24 and /26

| CIDR | Subnet Mask | Total IPs | Usable IPs | Example Range |
|------|--------------|------------|-------------|----------------|
| /24 | 255.255.255.0 | 256 | 254 | 192.168.1.0 – 192.168.1.255 |
| /26 | 255.255.255.192 | 64 | 62 | 192.168.1.0 – 192.168.1.63 |

So, `/26` is just a **smaller piece** of the `/24` network.

---

## Real Life Example

Imagine a company has one big network: `192.168.1.0/24`  
They want to give each department its own smaller subnet.

They can divide it like this:

| Department | Subnet (CIDR) | IP Range | Usable IPs |
|-------------|----------------|-----------|-------------|
| HR | 192.168.1.0/26 | 192.168.1.1 – 192.168.1.62 | 62 |
| IT | 192.168.1.64/26 | 192.168.1.65 – 192.168.1.126 | 62 |
| Sales | 192.168.1.128/26 | 192.168.1.129 – 192.168.1.190 | 62 |
| Finance | 192.168.1.192/26 | 192.168.1.193 – 192.168.1.254 | 62 |

Each subnet uses CIDR to show how much of the IP address is for the network.

---
