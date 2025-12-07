# Subnetting & CIDR

## 1. SUBNETTING

Subnetting means taking one big network and dividing it into smaller networks so IP addresses don’t get wasted and departments stay organized.

**Why we use Subnetting**

- To save IP addresses
- To separate teams (HR, IT, Finance)
- To improve security
- To reduce unnecessary network traffic

**Example :**

Big network: 192.168.1.0/24 → 256 IPs
You divide it into smaller parts:

- /26 → 64 IPs
- /27 → 32 IPs
- /30 → 4 IPs (router-to-router link)

**Useful Commands for Subnetting**

**Check your IP & Subnet Mask**
```
ipconfig        # Windows
ifconfig        # Linux/Mac
ip addr show    # Linux
```

**Find subnet information**
```
show ip interface      # Cisco
show ip route          # Cisco
netstat -r             # Linux
route print            # Windows
```

**Assign IP with Subnet Mask (Cisco)**
```
interface g0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
```

-------------------------------------------

## CIDR

CIDR (Classless Inter-Domain Routing) is simply a short way of writing subnet masks.

Instead of writing:
255.255.255.0
We write:
/24

The number after / shows how many bits belong to the network.

**Easy Examples:**

- /24 → 256 IPs
- /25 → 128 IPs
- /26 → 64 IPs
- /28 → 16 IPs
- /30 → 4 IPs

**CIDR Easy Rule**

- Bigger / = fewer IPs

- Smaller / = more IPs

**Useful Commands to See CIDR/Subnet Mask**

**Check mask in devices:**
```
ipconfig
ifconfig
ip addr show
```

**Check routing CIDR on routers**
```
show ip route
```

**Configure IP using CIDR (Cisco)**
```
interface g0/0
 ip address 10.10.10.1 255.255.255.192   # /26
```

