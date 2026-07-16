

**What is a Network?**

A series of devices that are all connected to each other

There are two types:

- Private network (like a home network)
- Public network (like the internet)

**What is the internet?**

A series of small private networks connected together via a public network

**IP Address**

Used to identify devices on a network

Can be public or private

Will change if device is connected to a different network, i.e someone else's house

Only 1 instance of an IP addy can be active on the same network at a time

Public addy identifies a device on the internet e.g a router, house looks like one single device to the internet

Public IP addies are given by ISP for monthly fee

Private addy identifies a device amongst other devices on a network and is never seen by the internet

Private IP addies are assigned by the network they connect to

IPv4 scheme's (old and limited as only goes up to 4.29 billion unique) addies are made up of 4 octets (8 bits) as such 192.168.1.1 ; each octet value adds up to be the IP addy of the device on the network via IP addressing and [[LAN (Local Area Network)#** Subnetting** | Subnetting ]] 

![[Pasted image 20260710104153.png]]

IPv6 is the new iteration of the addressing scheme. Supports 340 undecillion IP addies. More efficient cause of new mechanisms. e.g. 2a00:22c4:a531:c500:425f:cce6:c36b:f64d ; uses 8 hextets (16 bits) instead of 4 octets (8 bits)


**Mac Address**

All devices on a network have a physical network interface, being a microchip board on the device's mobo. Assigned unique addy at production factory called MAC address

MAC addy - 12 character hexadecimal num (base 16, 0 - 9 & A - F) split into pairs and separated by colons

first 6 characters = network interface producer | last 6 = unique number

![[Pasted image 20260710110701.png]]


Can be spoofed (faked), pretending to be another devices using it's MAC addy. Can break poorly implemented security designs that assume all devices talking on a network are trustworthy. 

e.g. Someone can spoof admin device MAC addy and trick firewall into thinking its receiving comms from the admin when it isn't


**Ping**

Uses ICMP packets to check performance of connection between devices, i.e. if the connection exists or is reliable

Time taken is measured by ping

**Summary**
- Network = A group of devices connected to one another on a LAN or VLAN
	- Can be connected to each other directly via Ethernet or backbone cables (Ring/Token and Bus topologies) 
	- Can also be connected to each other through the use of a switch (start topology)
	- Devices on a network can communicate with each other via the OSI Model
	- Can be public (Internet) or private (Home network)

- Internet = series of small networks connected to a larger public network
- IP address = Address used to identify host machine for numerous reasons (typically just used to find the MAC address on a machine via ARP)
	- Can be public or private
		- Public addy used to identify a device on an internet like a phone or a router, provided by ISP
		- Private addy is used to identify a device on a network like a home computer, assigned by network unless manually assigned.
	- Either IPv4 (old style) or IPv6 (modern style)
		- IPv4 - made up of 4 octets (8 bits), sum of octets = device IP address on network via IP addressing and subnetting 
		- IPv6 - made up of 8 hextets (16 bits), more efficient due to new mechanisms and offers wider range of available addresses (up to 340 undecillion) 
	- Only one instance of IP addy per network at a time
	- Changes if device moves to a different network

- MAC Address = Physical address of network capable device, burned into NIC during manufacture
	- 12 character Hexadecimal number (16 bit) split into pairs, separated by (:)
	- First 6 chars = NIC producer, Last 6 chars = unique num
	- Paired with IP addy during ARP to allow for device to be discovered by other devices on same network
	- Can be faked (spoofed) to make device appear as if it were another in order to gain access or data that the device shouldn't be able to have.

Ping - Both a tool and a unit of measurement used to check the performance of a connection to a host via ICMP packets

	*Note ICMP is blocked by many firewalls by default, just because a ping fails ≠ host is down, it often means firewall is silently dropping the packets