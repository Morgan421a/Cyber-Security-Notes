- IPv4 address configuration used to be manual
- **DHCP - Dynamic Host Configuration Protocol**
	- Released in 1997, updated through the years
	- Provides **automatic address / IP configuration**
	- Used for almost all devices

### DHCP Leases
- Automated process referred to as **DORA**
	- **Discover** - Find a DHCP server
	- **Offer** - Get an offer
	- **Request** - Lock in the offer
	- **Acknowledge** - DHCP server confirmation
- Occurs each time a device connects to the network for the first time and needs an IP address
##### Step 1: Discover
- **DHCP Discover** sent from **client** **(0.0.0.0/udp:68)** to **255.255.255.255:udp/67** as a **broadcast** (all devices on the local network/subnet will see it)
	- **255.255.255.255:udp/67** <- **Limited Broadcast address**, used as the **Destination IP address**
		- Ensures the message reaches all devices on the local network segment without being routed to other subnets <- Not routed due to hard coded drop rule for packets with the destination 255.255.255.255
##### Step 2: Offer
- **DHCP server** (e.g. **10.10.10.99:udp/67**) sees discover message from the client and sends a **DHCP Offer** as a **broadcast** to **255.255.255.255:udp/68** such that the client that sent the DHCP discover can see it
	- Multiple DHCP servers on a network = multiple offers to same client from which client can pick one
##### Step 3: Request
- **Client** (**0.0.0.0/udp:68**) Chooses one of the received offers and sends a **DHCP Request broadcast** to **255.255.255.255:udp/67**
##### Step 4: Acknowledgement
- **DHCP Acknowledgement** sent from DHCP **server** (e.g. **10.10.10.99:udp/67**) to **255.255.255.255:udp/68** as a **broadcast** to acknowledge that the IP address has been assigned to the **client** and that the address won't be assigned to another device for the **duration of the lease**
##### Lease Renewal
- Called **DHCP Renewal**
- Occurs when a device renews it's lease (while still connected, not a device reconnecting)
- Uses a shortened **DORA** of **just** **Request/ACK**
### DHCP Scopes
- Configured on the DHCP Server
- Includes:
	- IP address range, including excluded addresses that shouldn't be assigned (e.g. static addresses for switches or routers)
	- Subnet Mask
	- Lease Duration
	- Other Scope options include:
		- DNS Server
		- Default Gateway
		- VOIP (Voice Over IP) servers
##### DHCP Pools
- Within the scope of each DHCP server
	- Each subnet has its own scope
- Grouping of IP addresses for server to choose from in order to automatically assign IP addresses to a device
- Example pool:
	- 192.168.1.0/24
	- 192.168.2.0/24
	- 192.168.3.0/24
- Scope generally a single contiguous (unbroken sequence) pool of IP addresses
	- DHCP exclusions can be made inside of the scope (e.g. in the middle of the scope sequence)
### Address Reservation
- Administratively configured
- Allows a specific IP address to always be assigned to a specified device e.g. a router, file server, web server, etc.
- Removes the need to manually updated statically assigned addresses for devices on a network
- Done by configuring the **MAC address** of the device within the DHCP server itself
	- Each MAC address has a matching IP address
	- Uses a **MAC -to-IP mapping table**
- Also referred to by other names, such as:
	- Static DHCP Assignment
	- Static DHCP
	- IP Reservation
- Example of address reservation:
  ![[Pasted image 20260825082454.png]]