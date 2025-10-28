## Basic Configuration 

### Tasks: 
Power on devices & then configure the devices as follow :

<img width="600" height="150" alt="image" src="https://github.com/user-attachments/assets/79d32345-09d2-445b-9212-4d76ed54cf98" />
<br>

#### 1. Configure host names
   The hostname is the name of the router. It helps you identify each router in a network.
   For example:
   
    Router> enable                      (Go to router)
    Router# configure t                 (Enter setup mode)
    Router(config)# hostname Router1    (Give you router a name)
    Router1(config)# exit               (move back one level)
    Router1#                            (done)

   now will do same thing for Router2
    
    Router> enable       
    Router# configure t 
    Router(config)# hostname Router2  
    Router2(config)# exit  
    Router2# 
    
#### 2. Configure IP Addresses as shown in the diagram

    Router1(config)# int g0/0/0                             (enter the gigabitethernet interface for configuration)
    Router2(config-if)# ip address 10.1.1.2  255.255.255.0  (assign ip address with subnet mask)
    Router2(config-if)# end                                 (return to the main router)
    Router2# sh ip int gigabitEthernet 0/0/0                (it will shows th details oh that specific interface)
    
  will do samething for Router2
  
    Router2(config)# int g0/0/0
    Router2(config-if)# ip address 10.1.1.2  255.255.255.0
    Router2(config-if)# end
    Router2# sh ip int gigabitEthernet 0/0/0

    
3. Ensure routers can ping each other

   ```
     Router1# sh arp             (it shows ARP Table, means which devices are connected to your router by their IP & MAC addreses)
     Router1# ping 10.1.1.2      (it is used to check connectivity between router)
   ```
   
5. Configure an enable password of "cisco"
  
  ```
      Router1> en
      Router1# conf t
      Router1(config)# enable password cisco     (it is used to set a password for entering privileged EXEC mode on a router)
      Router1(config)# end
      Router1(config)# exit                      
      Router1> en                                (After exit we need to enable again for checking password if its showing)
      Password :
      Router1 :
  ```
  
6. Encrypt the enable password

 ```
      Router1> en
      Router1# conf t
      Router1(config)# service password-encryption     (it is used to hide (encrypt) all plain-text passwords in the router’s configuration)
      Router1(config)# end                     
      Router1# sh run
  ```
    
7. Configure a secret password of "cisco"

```
      Router1> en
      Router1# conf t
      Router1(config)# enable secret cisco123     (it is used to set an encrypted (hidden) password for entering privileged EXEC mode on a router)
      Router1(config)# end                     
      Router1# sh run
  ```
    
8. Configure the first 5 telnet lines and use a line password of cisco on them

   ```
      Router1> en
      Router1# telnet 10.1.1.2                   (Connect to another router with IP 10.1.1.2)
      Router1(config)# line vty 0 4              (Open lines for Telnet users)
      Router1(config-line)# login                (Tell router to ask for a password when someone uses Telnet)
      Router1(config-line)# password cisco       (Set Telnet password = cisco)
      Router1(config-line)# end                 
    ```
    
10. Configure a consol password of "cisco" and test

    ```
      Router1> en
      Router1# config t
      Router1(config)# line consol 0             (It is used to set a password for people who connect directly to the router using console cable)
      Router1(config-line)# login                (Tell router to ask for a password when someone uses Telnet)
      Router1(config-line)# password cisco       (Set Telnet password = cisco)
      Router1(config-line)# end

 Now when you open the router through console, it will ask for password “cisco”

     Router(config)# line console 0
     Router(config-line)# password cisco
     Router(config-line)# login
     Router(config-line)# end

     Router1> en
     Router1# copy running-config startup-config      (It will save your work permanently on the router)
     Router1# wr
          
    ```

 










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
