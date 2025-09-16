
# Networking Internship - 3 Months

This repository is a week-by-week documentation of my Networking Internship journey (3 months). It includes:

Key concepts learned each week

Hands-on practical labs and configurations

Troubleshooting exercises and case studies

The goal of this repository is to consolidate theoretical knowledge with practical exposure and serve as a reference for future learning in networking and related fields.

# weekly documentation

```
week 1
```
# Day 1
(https://claude.ai/public/artifacts/e92959cb-3269-4546-b97d-e5dcd0aee458)

# Day 2
(https://claude.ai/public/artifacts/f4b54e55-0e65-4185-8eb1-4ecbebbdf880)

# Day 3
(https://claude.ai/public/artifacts/9933647d-a377-4e9e-9b69-e1e4030a2a55)

## Task

### 1. Find out about ip class ranges (Private IPs) and Public IPs.
   # IP Address Basics

#### Private IPs
- Used inside **local networks (LAN/WiFi)**  
- Not visible on the Internet  
- Ranges:  
  - 10.0.0.0 – 10.255.255.255  
  - 172.16.0.0 – 172.31.255.255  
  - 192.168.0.0 – 192.168.255.255  

#### Public IPs
- Given by **ISP**  
- Used to identify you on the **Internet**  
- Example: 103.54.xx.xx  

#### Easy Example
- **Private IP** = Room number inside a house 🏠  
- **Public IP** = Full house address 📬

  

### 2. Explain Class A, Class B, Class C of Private IP ranges. Provide examples for each.
# Private IP Address Classes

#### Class A
- **Range:** 10.0.0.0 – 10.255.255.255  
- **Subnet Mask:** 255.0.0.0  
- **Hosts per Network:** ~16 million  
- **Example:** 10.1.5.20  

---

#### Class B
- **Range:** 172.16.0.0 – 172.31.255.255  
- **Subnet Mask:** 255.255.0.0  
- **Hosts per Network:** ~65,000  
- **Example:** 172.16.45.10  

---

#### Class C
- **Range:** 192.168.0.0 – 192.168.255.255  
- **Subnet Mask:** 255.255.255.0  
- **Hosts per Network:** 254  
- **Example:** 192.168.1.100  

---

## Quick Comparison Table

| Class   | Range                              | Subnet Mask      | Hosts per Network | Example        |
|---------|------------------------------------|------------------|------------------|----------------|
| Class A | 10.0.0.0 – 10.255.255.255          | 255.0.0.0        | ~16 million      | 10.1.5.20      |
| Class B | 172.16.0.0 – 172.31.255.255        | 255.255.0.0      | ~65,000          | 172.16.45.10   |
| Class C | 192.168.0.0 – 192.168.255.255      | 255.255.255.0    | 254              | 192.168.1.100  |




