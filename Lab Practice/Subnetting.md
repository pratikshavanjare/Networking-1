

<img width="1878" height="696" alt="Screenshot 2025-11-05 233552" src="https://github.com/user-attachments/assets/4ec09d9e-c7f8-4870-9715-558a85acbf06" />

Configure the network as follows:

1) You have been allocated subnet 192.168.1.0/24.

   Subnet this into four subnets as follows

2) Subnet 1 for site 1

3) Subnet 2 for the link between R1 and the Internet Router

4) Subnet 3 for site 2

5) Subnet 4 for the link between R2 and the Internet Router

6) Configure the routers per the instructions in the diagram.

7) Configure the switches with the second last IP address in the subnet

8) Configure the DHCP servers with the third last IP address in the subnet.

   And configure the DHCP server to allocate IP addresses to the clients

9) Verify that PCs can access cisco.com and facebook.com using their browsers



Let's do it Step by Step -

Firstly, will understand what is **SUBNETTING**? - It means dividing one big network into smaller networks. 
So, here in this lab we have main network that is - 192.168.1.0/24 that we will divide it into 4 subnets.
192.168.1.0/24 ---> 4 subnets

Let's divide it --

* Binary of 24 is -
  1111 1111. 1111 1111. 1111 1111. 0000 0000 = 24
  255      . 255      . 255      . 0         = Subnet Mask
  |______________________|       |_____|
          Network                 Host

Subnet means "Stealing" we will make a new ip address by changing their hosts. And the formula for calculating subnet is - 2^n

2^n ---->   Subnets 2^2 = 4 Subnets (Here 2^**2** is the number of bits that we stealing or using for the subnet portion)
2^n-2 ----> Hosts   2^3-2 = 6 Hosts (Here 2^**3**-2 is the number of bits that we will keep for the host portion)

So, for our network 192.168.1.0/24 we want 4 subnets. So, by applying formula we will be able to calculate subnets ---

192.168.1.0/24 ---------> 4 subnets
2^n ----------> subnets 2^2 = 4

So, the number of bits will be 2 for subnets that we will take from hosts.



| **Network**  | **Subnet** | **Host** |
|--------|--------------|--------------|
| 192.168.1. | 00 | 00 0000 | /26 



So , here 192.168.1.00 (Network+Subnet) can be written as in binary is 1111 1111. 1111 1111. 1111 1111. 00 and the Host part will be rest 00 0000  /26


| **Network**  | **Subnet** | **Host** |
|--------|--------------|--------------|
| 192.168.1. | 00 | 00 0000 = 192.168.1.0/26| 
| 192.168.1. | 01 | 00 0000 = 192.168.1.64/26| 
| 192.168.1. | 10 | 00 0000 = 192.168.1.128/26| 
| 192.168.1. | 11 | 00 0000 = 192.168.1.192/26| 

<img width="1810" height="751" alt="image" src="https://github.com/user-attachments/assets/936e61b1-1484-4804-8dfe-9d9b0fa0fc20" />


**Now, Firstly we will configure/create Subnet 1**

| **Network**  | **Subnet** | **Host** |
|--------|--------------|--------------|
| Net = 192.168.1. | 00 | 00 0000 = 192.168.1.0/26| 
| 1st = 192.168.1. | 00 | 00 0001 = 192.168.1.1/26| 

| 3rd Last = 192.168.1. | 00 | 11 1100 = 192.168.1.60/26| 
| 2nd Last = 192.168.1. | 00 | 11 1101 = 192.168.1.61/26| 
| Last = 192.168.1. | 00 | 11 1110 = 192.168.1.62/26| 
| Boadcast = 192.168.1. | 00 | 11 1111 = 192.168.1.63/26| 

"Broadcast address can be find ---> Have a look to the next subnet & subtractone to get to broadcast address to the previous subnet.

Firstly configure to **Router1**
```
R1 > en
R1# sh ip int brief
R1# config t
R1(config-if)# no shutdown
R1(config-if)# ip add 192.168.1.62 255.255.255.192
R1(config-if)# end
R1# sh ip
```

then **Switch1**
```
Switch> en
Switch# config t
Switch(config)# hostname S1
S1(config)# int vlan 1
S1(config-if)# no shut
S1(config-if)# ip add 192.168.1.61 255.255.255.192
S1(config-if)# end
S1# sh ip int brief
S1# wr
```

then **Server1**
```
IP add -----> 192.168.1.60 (config-> Fa0)

              255.255.255.192

Default Gateway -----> 192.168.1.62 (config-> Settings)

                        8.8.8.8

Services -----> DHCP --> click to the toggle button to on "service"
                         Default Gateway - 192.168.1.62
                         DNS - 8.8.8.8
                 Start IP add -------> 192    168    1    1
                 Maximum no. of users ---> 50
```
