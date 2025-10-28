#### Basic Configuration 










# vlan creating in single switch --

## Step 1: Enter Switch Configuration Mode

enable
configure terminal

## Step 2: Create VLANs

vlan 10
name Sales
exit

vlan 20
name Marketing
exit

## Step 3: Assign VLAN to Ports

interface FastEthernet 0/1
switchport mode access
switchport access vlan 10
exit

interface FastEthernet 0/2
switchport mode access
switchport access vlan 20
exit

## Step 4: Verify VLANs
show vlan brief


# 🖧 Router Connectivity with Switch and PCs

## 🎯 Objective
To connect a router with a switch and PCs, assign IP addresses, and verify network connectivity.

---

---

## ⚙️ Step 1: Configure Router Interface
```bash
Router> enable
Router# configure terminal
Router(config)# interface fastethernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# exit

## Step 2: Configure PCs

Set IP details in each PC (in Packet Tracer → Desktop → IP Configuration)

Device	IP Address	Subnet Mask	Default Gateway
PC1	192.168.1.2	255.255.255.0	192.168.1.1
PC2	192.168.1.3	255.255.255.0	192.168.1.1


## Step 3: Connect Devices

Router → Switch using straight-through cable

PCs → Switch using straight-through cables

After connecting, all interfaces should turn green (up/up) in Packet Tracer.

## Step 4: Verify Connectivity
From PCs:
PC> ping 192.168.1.1   # Ping Router
PC> ping 192.168.1.3   # Ping another PC
From Router:
Router# ping 192.168.1.2   # Ping PC1
Router# ping 192.168.1.3   # Ping PC2
If ping replies are successful → network is working properly.

Step 5: Save Configuration
Router# copy running-config startup-config
