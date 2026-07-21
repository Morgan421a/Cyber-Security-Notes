- Network = a group of devices all connected to each other such that they can communicate and transmit data to one another
	- Different topologies for a network:
		- Star:
			- Currently most common, All devices connected to a dedicated networking device such as a switch via Ethernet cables
			- Expensive due to need for dedicated networking device and lots of Ethernet cable, requires more maintenance especially at larger scales
			- If central network device breaks then network is down for all devices on said network
			- Scalable, easy to troubleshoot
			- if one device connected to network breaks the rest will still work as normal
		- Bus:
			- Devices connected and communicate via a singular backbone cable through which traffic travels
			- Devices branch off at different points of backbone cable like leaves on a branch
			- Prone to slowing and bottlenecking since all data travels along the same cable, single point of failure on backbone cable can break whole network, harder to scale since more devices connected = more traffic = higher likelihood of bottlenecking
			- Cheap due to less cabling and no need for dedicated networking device easier to setup
		- Ring/Token:
			- Devices connected directly to each other using Ethernet cables, data travels through each device on path to target host and gets forwarded by each device until target host is reached
			- Slower since data has to stop at each device first and will only be forwarded if current device has no data of its own to send, prone to bottlenecking if high traffic builds up as data only travels in one direction (unless double ring config). Single point of failure (device or cable) = network becoming inaccessible past certain device <- preventable with dual-ring config
			- Cheap since no need for dedicated networking device, easy to set up and troubleshoot

- Internet = A bunch of small networks (subnets) connected to each other on a larger public network

- IP address = Address used to find target host during communication over a network
	- Two versions:
		- IPv4 = Older, uses 4 octets (8 bits, 0-255 i.e 192.168.1.1, only supports 4.29 billion addresses
		- IPv6 = Newer, uses 8 hextets (16 bits, 0-9 & A-F) i.e. 2a00:22c4::425f:cce6:c36b:f64d, consecutive colons (::) = group of zeros used to fill in remaining hextets (will always be grouped together never spread throughout address), supports over 340 undecillion addresses

		- Same IP addy can't exist more than once at a single time on the same network
		- Can be Public or Private:
		- Public = Provided by ISP, allows networks to connect to each other so devices on different networks can communicate without seeing each other's private IP addies
		- Private = Assigned automatically upon connecting to a network (unless manually assigned), Used by devices on the same network to identify and communicate with each other
	- IP addresses -> 192.168.100.254/24 split into parts:
		- 192.168.100 = network
		- X.X.X.254 = host
		- /24 = which parts identify the network; in this case the first 24 bits = network so the first 3 octets of the address in this case because 24/8 = 3
		- Default gateway typically ends in .254 or .1 (human assigning convention) and usually denotes the router or layer 3 switch's IP address

- MAC Address = 12 character hexadecimal number burned onto the NIC installed on the mobo of network capable devices. 
	- Split into two parts and separated by colons:
		- First half = manufacturer
		- Second half = unique number
	- Can be spoofed to make devices think a device is a different one i.e thinking a device is the admin when it isn't, which can lead to data being sent or received to an unauthorised device

- Ping = Uses ICMP packets to check speed and reliability of a connection, results are measured in ping
- LAN = A network of devices in the same physical location i.e network in a home
- Switch = networking device used to connect local devices to each other on the same network by plugging each device into it using Ethernet cables and storing their MAC Address on a MAC address table, two commonly used types include:
	- Layer 2 switch - Only connects devices on the same network to each other, cannot connect to other networks without an external router
	- Layer 3 switch - Can connect devices on the same network to each other as well as connecting other networks via its routing capabilities, however lacks some routing features to connect devices to the wider internet
- Router = networking device that uses routing to connect networks to each other whether that be connecting subnets or connecting devices to the wider internet. Uses a default gateway to enable data to enter and exit its network
- ARP = Address resolution protocol, sits between layer 2 (data link) and layer 3 (network) to resolve IP addresses to MAC addresses so that incoming data can find the target device on a network as well as giving outgoing data the information needed for the target host to send data back to the sending device
- DHCP = Dynamic Host Configuration Protocol, automatically assigns IP addresses to devices connected to its network that don't yet have one using requests and replies between the client and the DHCP server:
	- DHCP Discover - client asks if there are any available IP addresses on the network
	- DHCP Offer - Server replies with an available IP address
	- DHCP Request - client receives response and requests the offered IP address
	- DHCP ACK - Server acknowledges the process is complete and client can now use address

- Subnetting = Splitting up a large network into smaller networks whether through physical methods such as LAN connections or logical methods such as VLAN
	- Requires routers or a layer 3 switch for each subnet so they can communicate with other subnets though not required if wanting to keep subnets separate
	- Improves efficiency and security of subnets
	- Uses a subnet mask to define max number of devices on a subnet:
		- 32 bit number that splits IP address into network and host portions, telling the device which part identifies the subnet

- OSI model = Open System Interconnection, provides a framework through which devices send and receive data. Enables normalisation of data transfer so different types and makes of devices can communicate with each other.
	- Comprised of 7 layers running 7 - 1 for sending data and 1 - 7 for receiving data
	- Each layer adds more information, process called encapsulation
	- Layers are:
		1. Physical - Physical equipment such as Ethernet cables that use electrical signals to represent raw bits for data transfer
		2. Data Link - occurs at switches, encapsulates the data into a frame, adding the sending and destination device's MAC addresses. Switch uses its MAC Address Table to determine which port to forward the frame out of.
			- ARP happens here to pair the device's IP address and the MAC address
		3. Network - where routing happens (layer 3 switch or router), uses OSPF and RIP to find most optimal path for packet to travel through 
		4. Transport - Where the most appropriate transport protocol is chosen TCP or UDP, done by firewalls load balancers, layer 4 switches
			- TCP Slower but more reliable, requires constant connection or sync between the two devices via the three way handshake
			- UDP Faster but less reliable, stateless but doesn't check if all packets were delivered correctly
		 5. Session - Creates a session between the two devices once connection is established, session allows packet travel across the connection without the risk of crossing into other sessions.
			- Uses checkpoints such that if a packet is dropped or fails to arrive correctly the device just needs to send the currently missing packet before continuing instead of restarting the whole transfer
			- Automatically closes connection after being idle (no traffic) for a certain amount of time
		6. Presentation - standardises the way in which data is formatted, such that it can be read by any device receiving it, also where security features occur i.e. encryption
			- Software based
		7. Application - The software which sets out rules on how users can interact with data, usually have a Graphical User Interface (GUI)

- Packets = data from layer 3 which contains information such as IP headers and the payload
	- IP headers include:
		- Source Address - sending devices IP address
		- Destination Address - Target host's IP address
		- Protocol Type - The type of protocol used to transport data, usually TCP/UDP
		- Time To Live (TTL) - How long a packet will exist before it expires
		- Checksum (IPv4 only not in IPv6) - Sum and result used to check data integrity

- Frames = data from layer 2 which encapsulates the packet and adds information such as the MAC address

- TCP/IP and UDP/IP = The selected protocol used for transporting data, both share some headers that are separate from the IP headers:
	- Checksum - separate from IP checksum header
		- TCP = mandatory in both IPv4 and IPv6
		- UDP = mandatory is IPv6, optional but recommended in IPv4
	- Source Port - the port through which data was sent
	- Destination Port - the port for which data is destined
	- data - the payload

 - TCP/IP also has the headers:
	 - Flags - SYN,ACK,FIN,RST,URG,PSH
	 - Sequence number - used to ensure data delivered in correct order
	 - Acknowledgement number- Added after data given a sequence number, next piece of data = sequence number + 1

- TCP = Stateful -> constant connection or device sync required - Better for large data transfer or where data integrity is essential i.e. transferring files
- UDP = stateless -> constant connection or device sync not needed - Better for small data transfer or where data integrity is optional i.e. video streaming

- The Three Way Handshake = Used to establish connection between devices via the sending of special messages with flags:
	1. SYN - client requests sync with target host and sends its ISN (100)
	2. SYN/ACK - target host acknowledges client's sync request and ISN and sends its own sync request and ISN (5000)
	3. ACK - client acknowledges target host's sync request and ISN and devices are now connected

- Four Way Handshake (Closing the connection)
	1. FIN - one device requests end of connection/sync
	2. ACK - other device acknowledges closure request
	3. FIN - other device sends own closure request
	4. ACK - initial device acknowledges other device's request and connection is closed both ways
- Extra flags
	- RST - Ends connection abruptly, usually indicates issue with connection process
	- DATA - Flag used when devices send data across connection, uses sequence numbers to ensure data delivered in correct order <- only used after the devices have finished the TWH and connection is established

- Ports = The points at which data is sent to or from a device
	- Developers follow rules which create order by ensuring specific types of data are sent to its standard port i.e. web servers all sending data to port 80 so it doesn't matter what browser is used they interpret the data the same way
	- Port used can be changed by developer of an app but a colon (:) must be used in front of it
	- Apps will assume standard port is being used unless told otherwise
	- Can be any number between 0 - 65535
	- Common ports are those between 0 - 1024
	- Some of the most common ports include:
		- 80 (HTTP) and 443 (HTTPS) For interacting with web servers
		- 21 (FTP) and 445 (SMB) For transferring and interacting with files
		- 22 (SSH) and 3389 (RDP) For remote interaction with devices and servers

- Port Forwarding - Configured at the router, allows for connection to the internet by opening specific ports to allow data transfer

- Firewalls - Controls the traffic entering a network, can be configured by the admin to either reject (with response) or drop (silently with no response) incoming packets if they match the rules outlined during configuration.
	- Can be stateful:
		- Analyses the entire connection and will block the device if the connection is poor or behaving unexpectedly i.e. odd behaviour during the three way handshake
		- Uses more resources but is more secure thanks to dynamic decision making
	- Or stateless:
		- Analyses each incoming packet and drops the ones that match the rules outlined by the admin during configuration
		- Better for high volumes of traffic and uses less resources
		- Due to rigid following of config rules is dumber than stateful and open to bypassing via loopholes or missing rules

- VPNs = Virtual Private Networks, used to create a private network between devices, even if nowhere near each other, through setting up a tunnel in which data can travel
	- Uses different technologies each with their own advantages and disadvantages, some are:
	- PPP = Point-to-Point Protocol - Used by PPTP to provide data encryption and allow for data authentication
	- PPTP = Point-to-Point Tunnelling Protocol - Allows data from PPP to travel and leave a network -> easy setup, widely supported but weaker encryption than other technologies
	- IPSec = Internet Protocol Security - Encrypts data via existing IP framework -> strong encryption and widely supported but more difficult to setup compared to alternatives
- VPNs:
	- Offer Privacy through encryption
	- Offer pseudo-anonymity <- Only as far as provider doesn't keep logs, user doesn't log into any personal accounts and as other devices on the network respect said anonymity

- VLAN = Virtual Local Area Network, allows devices to be connected on the same network without needing to be physically connected (by cabling), instead they are logically connected (by software config), while keeping them isolated from other VLANs
	- Setup using switches both layer 2 and layer 3 with some differences regarding connection to other subnets (layer 2 = devices on same subnet only, layer 3 = devices on other subnets as well as own)