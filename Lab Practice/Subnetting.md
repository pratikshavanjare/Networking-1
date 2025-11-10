

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

**Network**   |    **Subnet**   |   **Host**
192.168.1.    |      00         |     00 0000/26

| **Network**  | **Subnet** | **Host** |
|--------|--------------|--------------|
| 192.168.1. | 00 | 00 0000 | /26 |
  |             |
  |             |
  |             \----------------|
 \/                              \/
1111 1111. 1111 1111. 1111 1111. 00  = 26
