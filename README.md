This is a simple office network which consists of 3 departments connected with eachother through 1 switch and 1 router.

Being a small network, the company network has the following characteristics:
a) One router and one switch are used. (CISCO products in this project) <br>
b) 3 departments (Admin, Finance and Reception)
c) Each department is in different VLAN
d) Each department have a wireless network (Access point) for users
e) Host devices in the network can obtain IPv4 address automatically
f) Devices in all departments can communicate with each other
g) Devices from different departments can connect to any access point in the network

Base network IP is 192.168.1.0 

No. of subnets = 3 (since there are 3 departments)
No. of subnets = 2^n  where n is no. of borrowed network bits
Now,
2^n = 3  
Here, n = 2 since 2^2 = 4 > 3 (we cannot use n=1 because that would result in 2^1 = 2 < 3)

Subnet Mask = 255.255.255.0 since base network IP is Class C
Now, we convert the subnet mask in binary form,
255.255.255.0 = 11111111. 11111111. 11111111. 00000000
Now after borrowing 2 bits, we replace with 11 from left to right,
11111111. 11111111. 11111111. 11000000
Now, converting it in decimal, we get,
New subnet mask = 255.255.255.192
Block size = 64 

--------- 1st Subnet --------- 
Network ID: 192.168.1.0
Broadcast ID: 192.168.1.63
Host Range: 192.168.1.1 - 192.168.1.62
IP: 192.168.1.0/26 (because 192 subnet mask corresponds to 26 CIDR)

--------- 2nd Subnet ---------
Network ID: 192.168.1.64
Broadcast ID: 192.168.1.127
Host Range: 192.168.1.65 - 192.168.1.126
IP: 192.168.1.64/26 (because 192 subnet mask corresponds to 26 CIDR)

--------- 3rd Subnet ---------
Network ID: 192.168.1.128
Broadcast ID: 192.168.1.191
Host Range: 192.168.1.129 - 192.168.1.190
IP: 192.168.1.128/26 (because 192 subnet mask corresponds to 26 CIDR)



Configured the router with Default gateway: 192.168.1.1 for VLAN 10
Configured the router with Default gateway: 192.168.1.65 for VLAN 20
Configured the router with Default gateway: 192.168.1.129 for VLAN 30

We are only using 9 ports of the switch and hence we configured the switch for 3 ports each for each VLAN, so,
Ports 2,3 and 4 = VLAN 10
Ports 5,6 and 7 = VLAN 20
Ports 8,9 and 10 = VLAN 30

