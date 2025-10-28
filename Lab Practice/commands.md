## Basic Configuration 

#### Tasks: 
Power on devices & then configure the devices as follow :

<img width="600" height="150" alt="image" src="https://github.com/user-attachments/assets/79d32345-09d2-445b-9212-4d76ed54cf98" />

#### 1. Configure host names
   The hostname is the name of the router. It helps you identify each router in a network.
   For example:
   
    Router> enable       (Go to router)
    Router# configure t  (Enter setup mode)
    Router(config)# hostname Router1  (Give you router a name)
    Router1(config)# exit  (move back one level)
    Router1# (done)

   now will do same thing for Router2
    
    Router> enable       (Go to router)
    Router# configure t  (Enter setup mode)
    Router(config)# hostname Router2  (Give you router a name)
    Router2(config)# exit  (move back one level)
    Router2# (done)
    
#### 2. Configure IP Addresses as shown in the diagram

    Router1(config)# int g0/0/0    (enter the gigabitethernet interface for configuration)
    Router2(config-if)# ip address 10.1.1.2  255.255.255.0  (assign ip address with subnet mask)
    Router2(config-if)# end        (return to the main router)
    Router2# sh ip int gigabitEthernet 0/0/0       (it will shows th details oh that specific       interface)
    
  will do samething for Router2
  
    Router2(config)# int g0/0/0
    Router2(config-if)# ip address 10.1.1.2  255.255.255.0
    Router2(config-if)# end
    Router2# sh ip int gigabitEthernet 0/0/0

    
3. Ensure routers can ping each other

   ```
     Router1# sh arp  (it shows ARP Table, means which devices are connected to your router by       their IP & MAC addreses)
     Router1# ping 10.1.1.2      (it is used to check connectivity between router)
   ```
   
5. Configure an enable password of "cisco"

   
  
6. Encrypt the enable password
    
7. Configure a secret password of "cisco"
    
8. Configure the first 5 telnet lines and use a line password of cisco on them
    
9. Make sure you can telnet from one device to the other
    
10. Configure a consol password of "cisco" and test










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
