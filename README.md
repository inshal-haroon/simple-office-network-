This is a simple office network which consists of 3 departments connected with each other through 1 switch and 1 router. This project is created using Cisco Packet Tracer v.7.3.0.0838

Being a small network, the company network has the following characteristics: <br>
a) One router and one switch are used. (CISCO products in this project) <br>
b) 3 departments (Admin, Finance and Reception) <br>
c) Each department is in different VLAN <br>
d) Each department have a wireless network (Access point) for users <br>
e) Host devices in the network can obtain IPv4 address automatically <br>
f) Devices in all departments can communicate with each other <br>
g) Devices from different departments can connect to any access point in the network <br>

Base network IP is 192.168.1.0  <br>

No. of subnets = 3 (since there are 3 departments)   <br>
No. of subnets = 2^n  where n is no. of borrowed network bits <br>
Now,   <br>
2^n = 3  <br>
Here, n = 2 since 2^2 = 4 > 3 (we cannot use n=1 because that would result in 2^1 = 2 < 3)  <br>

Subnet Mask = 255.255.255.0 since base network IP is Class C    <br>
Now, we convert the subnet mask in binary form,     <br>
255.255.255.0 = 11111111. 11111111. 11111111. 00000000      <br>
Now after borrowing 2 bits, we replace with 11 from left to right,     <br>
11111111. 11111111. 11111111. 11000000      <br>
Now, converting it in decimal, we get,     <br>
New subnet mask = 255.255.255.192     <br>
Block size = 64     <br>

--------- 1st Subnet ---------       <br>
Network ID: 192.168.1.0    <br>
Broadcast ID: 192.168.1.63    <br>
Host Range: 192.168.1.1 - 192.168.1.62      <br>
IP: 192.168.1.0/26 (because 192 subnet mask corresponds to 26 CIDR)     <br>

--------- 2nd Subnet ---------      <br>
Network ID: 192.168.1.64     <br>
Broadcast ID: 192.168.1.127     <br>
Host Range: 192.168.1.65 - 192.168.1.126     <br>
IP: 192.168.1.64/26 (because 192 subnet mask corresponds to 26 CIDR)    <br>

--------- 3rd Subnet ---------      <br>
Network ID: 192.168.1.128      <br>
Broadcast ID: 192.168.1.191     <br>
Host Range: 192.168.1.129 - 192.168.1.190     <br>
IP: 192.168.1.128/26 (because 192 subnet mask corresponds to 26 CIDR)     <br>



Configured the router with Default gateway: 192.168.1.1 for VLAN 10     <br>
Configured the router with Default gateway: 192.168.1.65 for VLAN 20    <br>
Configured the router with Default gateway: 192.168.1.129 for VLAN 30    <br>

We are only using 9 ports of the switch and hence we configured the switch for 3 ports each for each VLAN, so,
Ports 2,3 and 4 = VLAN 10
Ports 5,6 and 7 = VLAN 20
Ports 8,9 and 10 = VLAN 30

