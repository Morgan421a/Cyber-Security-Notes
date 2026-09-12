### LANs
- **Local Area Networks**
	- A group of devices in the same broadcast domain
		- e.g. separate switches = separate broadcast domains
	- Devices **separated physically** via individual switches for each broadcast domain

### Virtual LANs (VLAN)
- **Virtual Local Area Networks**
	- A group of devices in the same broadcast domain
	- Assigning different interfaces on a switch to belong to a particular VLAN
		- e.g. assigning 4 interfaces on a switch to one VLAN and 6 different interfaces to another VLAN
	- Each VLAN = Separate broadcast domain
		- VLANs cannot see each other's traffic
- Devices **separated logically** (on the same switch) rather than physically (i.e. using different switches)
- Routers are needed to allow devices on different VLANs to communicate with each other
	- **Some switches** have built in routing functionalities (e.g. layer 3 switch), otherwise an **external router** would need to be used

### Configuring VLANs
- Example:![[Pasted image 20260825090252.png]]
	- Red = VLAN 1 : Gate room
	- Blue = VLAN 2 : Dialing room
	- Green = VLAN 3 : Infirmary
- Devices on each VLAN can't communicate with devices on different one

### VPNs
- **Virtual Private Networks**
	- Allows devices to communicate across a network but encrypts all data being sent over the network
	- Encrypted (private) data traversing a public network
	- Can also be used by organisations to allow for remote access of internal resources as if physically on the LAN
- **Concentrator** = Device used to encrypt/decrypt data in real time
	- Often integrated into a firewall or a purpose-built appliance
- Many deployment options:
	- Specialised cryptographic hardware
	- Software-based
- Used with client software
	- Sometimes built into the OS
	- Third party software can be installed onto an OS
##### Client-to-site VPN
- In the context of working from home:
	- Client = the user
	- Internet sits between Client and Site
	- Site = Concentrator at a central point, typically at the edge of a larger corporate network
- Data sent over the network is always encrypted and therefore protected
- Can be configured as an **Always on config**
	- Once client is powered on, link to concentrator is automatically connected
		- Removes need to manually start VPN software
		- If client is on the network and connected to the internet the encrypted channel to the concentrator is there
##### Site-to-site VPN
- In the context of a large organisation:
	- Corporate network at a central location and remote sites at other physical locations
	- **Site-to-site VPN** commonly used to connect similar setups
	- Almost **always-on**
	- Typically implemented using **firewalls**
		- Firewalls act as **VPN Concentrators**
			- Firewall connecting to corporate network
			- Internet sits between both
			- Separate firewall connecting to a remote site
	- Data sent between central location and remote site via the concentrators will always be going through an **encrypted channel**