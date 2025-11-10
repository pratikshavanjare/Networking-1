## L2 Switch Implementation 
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/d30d4b74-24c4-4c64-9214-a4a7b8e6b2c5" />

Here our objective is to configure VLANs on a Layes 2 switch, assign ports to VLANs & verify connectivity within the same VLAN.

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/5bc9c789-1be2-4db2-86b3-2910aedc6479" />

Let's solve it in packet tracer, Here will configure below step by step - 

### 1 Planning
- Design an IP addressing scheme for each VLAN.
- Identify which ports will belong to which VLAN.

| VLAN ID | VLAN Name | Network | Assigned Ports |
|----------|------------|----------|----------------|
| 10 | Sales | 192.168.10.0/24 | Fa0/1, Fa0/2 |
| 20 | HR | 192.168.20.0/24 | Fa0/3, Fa0/4 |

---

### 2 VLAN Creation
```bash
enable
configure terminal

vlan 10
 name Sales
exit

vlan 20
 name HR
exit
```

### 3 Assign Ports to VLANs
```
interface fastEthernet0/1
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
exit

interface fastEthernet0/2
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
exit

interface fastEthernet0/3
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
exit

interface fastEthernet0/4
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
exit
```

### 4 Verify VLAN Configuration
```
show vlan brief

```

### 5 Test Connectivity
From PC1
```
ping 192.168.10.4
```
---------------------------------



## L3 Switch Implementation 

<img width="700" height="450" alt="image" src="https://github.com/user-attachments/assets/2db736b4-0ea9-4755-9c05-5651371f3e6c" />

Here our objective is to configure VLANs on a 3 Layer switch, enable inter-VLAN routing, verify communication between different VLANs.

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/16521d6f-a9cb-451e-83c9-17753f4b94fc" />


##  Configuration Steps

### 1️ Planning
Design IP addressing and VLAN scheme.

| VLAN ID | VLAN Name | Network | Gateway (SVI IP) |
|----------|------------|----------|------------------|
| 10 | Sales | 192.168.10.0/24 | 192.168.10.1 |
| 20 | HR | 192.168.20.0/24 | 192.168.20.1 |

---

### 2️ VLAN Creation
```bash
enable
configure terminal

vlan 10
 name Sales
exit

vlan 20
 name HR
exit
```

### 3 Assign IP Interfaces
```
interface vlan 10
 ip address 192.168.10.1 255.255.255.0
 no shutdown
exit

interface vlan 20
 ip address 192.168.20.1 255.255.255.0
 no shutdown
exit
```

### 4 Enable IP Routing
```
ip routing
```

### 5 Assign Access Ports to VLANs
```
interface fastEthernet0/1
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
exit

interface fastEthernet0/2
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
exit
```

### 6 Verify Configuration
```
show vlan brief
show ip interface brief
show running-config
```

### 7 Test Inter-VLAN Connectivity
From PC1
```
ping 192.168.10.4
```
------------------------------------------------------

## Design VLANs for a small office
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/0b65a2f4-3ecb-4efb-9a6c-d1120c94712d" />

Let's do it on packet tracer step by step -

<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/8edb4981-1915-4b61-8813-0086e950cc63" />

### 1 VLAN Configuration on L3 Switch
```
enable
configure terminal

! --- Create VLANs ---
vlan 10
 name HR
exit

vlan 20
 name IT
exit

vlan 30
 name SALES
exit

vlan 99
 name MGMT
exit
```

### 2 Assign Ports to VLANs
```
interface range fa0/1 - 3
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
exit

interface range fa0/4 - 6
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
exit

interface range fa0/7 - 9
 switchport mode access
 switchport access vlan 30
 spanning-tree portfast
exit
```

### 3 Create VLAN Interfaces for Inter-Vlan Routing
```
ip routing

interface vlan 10
 ip address 192.168.10.1 255.255.255.0
 no shutdown
exit

interface vlan 20
 ip address 192.168.20.1 255.255.255.0
 no shutdown
exit

interface vlan 30
 ip address 192.168.30.1 255.255.255.0
 no shutdown
exit

interface vlan 99
 ip address 192.168.99.1 255.255.255.0
 no shutdown
exit
```

### 4 Check Connectivity
```
ping 192.168.20.10
```
