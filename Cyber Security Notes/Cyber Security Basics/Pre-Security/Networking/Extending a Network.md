**Car Park:**

**Port Forwarding**
- Configured at router of a network
- Allows apps and services to be connected to the internet
- Opens specific ports
- Not to be confused with a firewall

**Firewalls**
- Device within networks responsible for determining what traffic is allowed to enter and exit
- Admins can configure to permit or dent traffic from entering or exiting based on many factors such as:
	- Where traffic is coming from
	- Where traffic is going to
	- What port is traffic for
	- What protocol is traffic using
- These are answered via packet inspection
- Size and shape can vary i.e dedicated pieces of hardware typically used for a large amount of data to residential routers like in a home.
- Can also be software like Snort
- Firewalls can fall into 2 to 5 categories, 2 primary ones being:
	1. Stateful:
		- Inspects all info from a connection instead of individual packets
		- determines behaviour of device based on entire connection
		- Blocks entire device if host's connection is bad 
		- High resource cost compared to stateless firewalls due to dynamic decision making. i.e. might allow the first parts of TCP handshake but fail on later ones
	2. Stateless:
		- Uses static rules to decide if individual packets are okay or not, i.e. one bad packet doesn't mean the entire device is blocked
		- Good when large amounts of traffic being received from set of hosts i.e. DDoS attack
		- Use fewer resources than other categories but are dumber, open to loopholes in rules being found


**VPN Basics**
 - Technology that allows devices on separate networks to communicate securely by creating a dedicated path between each other over the internet known as a tunnel
 - Devices connected within a tunnel form own private network
 - Allows networks in different geographical locations to be connected
 - Offers privacy via encryption 
 - Offers anonymity (dependent on whether or not other devices on private network respect privacy)  ==*See summary for correction but keep here for THM Certificate revision*==
 - VPNs use a private key and public certificate (similar to SSH), both must match for user to connect (Technically MPPE handles encryption here, certs are rare in PPTP, THM simplified point)
 - Some VPN technologies are:
	 - PPP
	 - PPTP
	 - IPSec

**LAN Networking Devices**
- Router:
	- Dedicated devices used to connect networks and pass data between them via routing
	- Operate at Layer 3 of OSI Model
	- Typically have an interactive interface such as a website or console that allows admins to configure rules like port forwarding or firewalling

- Switch:
	- Dedicated networking device used to connect multiple devices via Ethernet
	- Can facilitate 3 to 63 devices
	- Operate at Layer 2 and 3 of OSI Model yet are exclusive in that Layer 2 switches cannot operate at Layer 3
	- Layer 2 Switches' sole responsibility is to send frames to correct device
	- Layer 3 switches = more sophisticated as can perform some of the router's jobs such as both sending frames to devices (like Layer 2 router) and route packets to other devices using IP protocol

- Also used to set up VLANs:
	- Layer 2 switches can allow devices on the same VLAN to communicate with each other allowing for device network isolation. However they cannot route traffic between the different VLANs i.e one department can't communicate with another if they're on a different VLAN
	- Due to built in routing capabilities, Layer 3 switches can route traffic between different VLANs by acting as a gateway for each VLAN, removing the need for an external router to allow for internal traffic flow. (External router/firewall still needed to connect devices to internet)

- Layer 3 switch = Intranet created for devices on same VLAN = Can also communicate with devices on other VLANs without need for external router
- Layer 2 switch = Intranet created for devices on same VLAN = Devices on same VLAN can communicate but network needs external router to enable communication to different VLANs
	- Both still need external router/firewall to connect to the internet


## **Summary**
- Port Forwarding - Allows apps and servers to be connected to the internet by opening specific ports
	- Where? = Configured on the router
	- Why? = Directs external internet traffic to a specific internal device
	- - Don't confuse with firewall
- Firewalls - Security measure configured with a set of rules decided by the admin. 
	- Will Reject (with a response) or drop (silently, no response) data that matches the rules to prevent potentially malicious or unwanted data from being received by a device.
	- Can be Stateless or Stateful:
		- Stateless = Inspects each packet and only drops the ones that match its configured rules, better for large amounts of traffic, fewer resources used but dumber than stateful
		- Stateful = Inspects entire connection and will block it if connection doesn't match the expected state of a legitimate handshake, uses more resources but is more robust in its security due to dynamic decision making
- VPN - Sets up a tunnel to allow devices to connect to each other over a secure private network. 
	- Many different types of technologies each with their own boons and caveats i.e. easier to set up & supported by more devices but less secure than another
	- Allows devices on completely geographically different networks to connect on the same network
	- Offers privacy through encryption 
	- pseudo-anonymity by masking user IP from the destination - dependent on whether VPN provider keeps logs or if user logs into personal accounts as well as if other devices on the network respect said anonymity
	
- LAN networking devices = Devices that allow for the creation/connection of a LAN network:
	- Switch: 
		- Layer 2 - allows for devices on the same local network to connect to each other through the use of Ethernet cables plugged into it and by using its MAC address table to find the target host for data transfer. 
			- In ref to VLANs Allow devices in physically different locations to connect logically (through software config instead of cabling) while keeping other VLANs separate but again cannot connect a network to other subnets without an external router 
		- Layer 3 - Allows for local network communication as well as communication with devices on other subnets across an entire LAN through the use of its routing features. Only has some routing features and thus cannot connect to the internet
			- In ref to VLANs, same as Layer 2 but again, can connect subnets through its routing features without the need for an external router
	- Router - Operates at layer 3 and can be used to connect subnets across a LAN as well as connecting them to the wider internet unlike the layer 3 switch