### IP Addressing
- IPv = Internet Protocol Version e.g. IPv4 = Internet Protocol Version 4
- **IPv4** is the **primary** **protocol** for everything
	- Included in almost all configurations
- **IPv6** is now part of all major operating systems
	- Has become the **backbone** of the **internet infrastructure**

### IPv4 Address
- **32-bit** address (4 bytes) 
	- separated into groups of 4, each group usually called an **octet** (8 bits/1 byte)
	- 1 byte = 8 bits
		- max decimal value for each byte = 255
			- e.g. 255.255.255.255 = maximum possible value
- Written in **Decimal Format** (base-10 system) -> **0-9**
- OSI **Layer 3** address
- example:
	- 192.168.1.131
		- 11000000.10101000.00000001.10000011 <- same as above but in its binary format
#### Public IPv4 Address
- Each **IPv4 address** on the **internet** is **unique**
	- e.g. one device's IP could be 1.1.1.1 and could communicate with a device with IP 2.2.2.2
- **IPv4** supports around **4.29 billion addresses**
	- **Scalability issue**, **estimated** to be around **20 billion devices** connected to the **internet** (**and growing**)
- Ways to **manage** the **demand** have been found such as:
	- **Network Address Translation (NAT)** -> Enable **private IP networks** to use the **internet** and **cloud** by **translating** **private IP addresses** in an internal network **to** a **public IP address** before packets are sent to an external network

### Private IP Address Ranges
- On the internet **public addresses** can **communicate** with **public addresses**
- On a **company network** there might only be **one public IP address** **linking** their **network** to the **internet**, but within the **private network** there may be **many devices** that can have a **private IP address** assigned to them
- Large Private IP address range
	- Allows for **networks** to be **properly designed** and **scaled easily**
- Private addresses **allow for devices within a network to communicate**
- **Private addresses are not internet-routable**
- Private addresses **don't go to, or pull from**, the **public pool of IPv4** and thus a private network can have thousands of devices, each with their own private address
	- Communication out to the internet can be done using a single IPv4 address instead of one for each device
- **Private address range defined in RFC 1918**
	- **RFC = Request For Comment**

### Public vs. Private Address
- **RFC 1918 Private IP Addresses**:

| IP address range              | Number of Addresses | Classful Description    | Largest CIDR block (Subnet mask) | Host ID Size |
| ----------------------------- | ------------------- | ----------------------- | -------------------------------- | ------------ |
| 10.0.0.0 - 10.255.255.255     | 16,777,216          | single class A          | 10.0.0.0/8 (255.0.0.0)           | 24 bits      |
| 172.16.0.0 - 172.31.255.255   | 1,048,576           | 16 contiguous class Bs  | 172.16.0.0/12 (255.240.0.0)      | 20 bits      |
| 192.168.0.0 - 192.168.255.255 | 65,536              | 256 contiguous class Cs | 192.168.0.0/16 (255.255.0.0)     | 16 bits      |
-  **10.0.0.0 - 10.255.255.255** <- Range typically used for the **largest private networks** e.g. large enterprise networks, data centres, cloud service providers, etc.
- **172.16.0.0 - 172.31.255.255** <- Typically used for **medium to large private networks** e.g. campus networks, cloud infrastructure, medium to large enterprise networks, etc.
- **192.168.0.0 - 192.168.255.255** <- Typically used by **small private networks** e.g. home routers, small offices, most consumer Wi-Fi devices

- **Classful Description** = Used to **divide IP addresses into "classes"** based on the **first few bits** of the address, **before CIDR existed**
	- Class A = Huge networks (first octet 0-127) -> Default subnet mask = 255.0.0.0
	- Class B = Medium networks (first octet 128-191) -> Default Subnet mask = 255.255.0.0
	- Class C = Small networks (first octet 192-223) -> Default Subnet mask = 255.255.255.0
		- **Subnet Mask** = what portion of address is **network part vs the host part**; **255** octet = **network**, **0** = octet available for **hosts** 

- **Largest CIDR Block** = **Modern notation** of **Classful Description** (replaced it entirely in 1993)
	- **CIDR = Classless Inter-Domain Routing**
	- Easier to say 10.0.0.0/8 than it is to say 10.0.0.0 to 10.255.255.255
	- /8 = 255.0.0.0 <- Class A (first octet 0-127) -> same as table, /8 (255.0.0.0), no bigger classful unit to group multiple class A networks under
	- /16 = 255.255.0.0 <- Class B (first octet 128-191) -> table /12 (255.240.0.0) = entire private block, has 65,536 class B /16s. /16 (255.255.0.0) = single class B network
	- /24 = 255.255.255.0 <- Class C (first octet 192-223) -> table /16 (255.255.0.0) = entire private block, has 256 class C /24s ./24 (255.255.255.0) = single class C network
		- **Subnet masks different in table** since they represent the CIDR blocks needed to cover entire private range (e.g. /12 for 172.16.0.0 - 172.31.255.255), not a single default classful network
	- **10.0.0.0/8 = One whole class A**
		- /8 (255.0.0.0) <- Octet 1 locked, host portion = full 2nd, full 3rd, & full 4th octets = 24 bits = 256 x 256 x 256 = 16,777,216 addresses
	- **172.16.0.0/12 = 16 class Bs merged**
		- /12 (255.240.0.0) <- Octet 1 and first 4 bits of octet 2 locked (hence /12), host portion = bottom 4 bits of 2nd & full 3rd & full 4th = 20 bits = 16 x 256 x 256 = 1,048,576 addresses
		- Split into /16 subnets (255.255.0.0), last 4 bits of octet 2 (4 fixed x 4 free = 16 possible values), 3rd octet is **subnet selector** (256 possible values (0 inclusive)), 4th octet is **host selector** (256 values per subnet)
			- 16 x 256 subnets = 4096 distinct /24 networks (each with 256 addresses)
				- 4096 x 256 hosts per subnet = 1,048,576 total number of addresses
	- **192.168.0.0/16 = 256 class Cs merged**
		- /16 (255.255.0.0) <- Octets 1 & 2 locked, so host portion is full 3rd & 4th octet = 16 bits = 65,536 addresses
			- Split into /24 subnets (255.255.255.0) 3rd octet becomes **subnet selector** (256 possible values (0 inclusive)), 4th octet becomes **host selector** (256 values per subnet)
				- 256 subnets x 256 hosts per subnet
					- 256 x 256 = 65,536 total number of addresses

- **Host ID Size** = How many bits are left over for numbering individual hosts (devices) once the network portion is defined
	- Is simple maths -> 32 bits - *CIDR prefix number*, for example:
		- /8 -> 32 - 8 = 24 host bits
		- /12 -> 32 - 12 = 20 host bits
		- /16 -> 32 -16 = 16 host bits
	- More host bits = more devices on the network

### IPv6 Addresses
- **IPv6 addresses = 128-bit length** (16 bytes)
	- Separated into groups of 8, each group = 16 bits/2 bytes/ 2 octets
- Written in **Hexadecimal Format** (base-16 system) -> **0-9 and A-F** (A-F represent **10-15**)
- Roughly **340 undecillion** addresses
- Example:
	- fe80::5d18:652:cffd:8f52
		- **Pair of colons (::)** = A **consecutive group of 0's**, as such the actual address is:
			- fe80:0000:0000:0000:5d18:0652:cffd:8f52
			- The **double colon** (::) can **only appear once** in an IPv6 address to **prevent ambiguity** during expansion
				- Can appear at the beginning, middle or end of the address:
					- Beginning -> ::fe80:5d18:652:cffd:8f52
					- Middle -> fe80::5d18:652:cffd:8f52
					- End -> fe80:5d18:652:cffd:8f52::
- Due to **IPv6 complexity**, **DNS** is **very important**
- First 64 bits usually the network prefix (/64)
- Last 64 bits usually the host network address
### Loopback Address
- A special **IP address** that **allows** a **device to communicate with itself**
	- Routes traffic internally without sending it to a physical network interface (e.g. Ethernet, Wi-Fi, etc.)
		- Works the same way regardless of whether an NIC is physically connected/enabled hence its usefulness for software testing
- Typically used for: 
	- Local testing
	- Troubleshooting network software
	- Ensuring the TCP/IP stack is functioning correctly
- **IPv4** Standard loopback address = **127.0.0.1** <- Falls within the reserved 127.0.0.0/8 range (127.0.0.0 - 127.255.255.255)
- **IPv6** Standard loopback address = **::1** <- represents the compressed form of 0:0:0:0:0:0:0:1
- Commonly referred to as **localhost**
- Essential for developers to test apps locally without external network dependencies
### APIPA
- **Automatic Private IP Addressing (APIPA)**
	- **Networking feature** that **allows** a **network client** to **discover** an **IP address** using its own **APIPA** in the event that **DHCP fails**
- **Specific to IPv4**
- Process:
	1. Client selects an address at **random** in the range **169.254.1.0 - 169.254.254.255** (inclusive), with a **subnet mask of 255.255.0.0**
	2. Client sends an **ARP packet** asking for the **MAC address** that corresponds to the randomly generated IPv4 address
	3. If another machine is using the address, the client will generate another random address and try again
- **Address range 169.254.0.0/16 set aside for "link local" addresses (first and last 256 addresses reserved for future use)**
	- **Should not be manually assigned or assigned using DHCP (RFC 3330)**
	- In many cases, presence of "link local" address indicates a loss of network connectivity, or that a DHCP server is down
- Only used if DHCP is activated
- **Means "no internet access"** - devices with a 169.254.x.x address can only talk to other devices on the same local segment, but can't reach beyond it
- Implemented in Windows 98 and later
	- Available in classic Mac OS 8.5 through 9 and in macOS
