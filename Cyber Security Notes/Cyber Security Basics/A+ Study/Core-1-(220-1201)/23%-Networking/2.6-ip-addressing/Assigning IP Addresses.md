### Networking With IPv4
- Every device needs a **unique** IP address
	- Can be assigned manually or configured in a service such as DHCP
- Devices on a network need a subnet mask e.g. 255.255.255.0
	- Used by the local device to determine what subnet it's on
	- Subnet mask isn't (usually) transmitted across the network
- Devices that need to communicate outside of their local network need to know the IP address of the local router <- Typically referred to as the **Default Gateway** e.g. 192.168.1.1
	- Router allows devices to communicate outside of their local subnet
	- **Default Gateway** must be an IP address on the local subnet

### Static IP Addressing
- An IP address that **doesn't change**
- Manually configure the IP 
	- e.g. Type it in from the keyboard on each device
- Can be **difficult to manage**
	- If the address changes, the device must be visited physically to type in the new parameters (IP, Subnet mask, gateway, etc.)
	- Doesn't Scale well for larger networks
- Should be avoided where possible
	- Better ways to **assign static addresses** exist, such as through: 
		- **DHCP reservations** <- Links the MAC address of a device to a specific IP address on the DHCP server, server will always assign the same IP address to that device from there on

### Automatic Private IP Addressing (APIPA)
- An **IPv4 link-local address**
	- **Not forwarded** by **routers** <- No routing outside of subnet = No internet connectivity
- Allows devices to communicate within their local IP address subnet
- APIPA standard sets a block of addresses that can be used for the **link-local** address:
	- **169.254.0.0 - 169.254.255.255** <- Subnet mask of /16 due to 16 available bits (0.0) for subnet and host selector
		- **First and last 256 addresses** are **reserved**, therefore the **functional block** is:
			- **169.254.1.0 - 169.254.254.255** <- The address range devices will receive from
- If a device is using an APIPA address it means it has assigned itself said address
	- May mean the DHCP address isn't communicating and needs troubleshooting
- A **device** **randomly assigns** itself and address from the block and uses **ARP** to ensure the address isn't currently in use
	- If it is in use it simply chooses another address at random and checks again using **ARP**

### Turning Dynamic Into Static
- **DHCP** assigns the **first available IP address** from a large pool of addresses (address pool is contiguous) 
	- **IP address** will **occasionally** **change** -> DHCP lease expires without a renewal so another device may grab the previously used IP address
- **Static IP addressing** can be used where a device's **IP address shouldn't change**
	- e.g. Server, Printer, Router, or even personal preference
- **DHCP** could be **disabled** on devices where **static IP addressing** is desired and manually configure the IP address config settings
	- **Better**, and more common, to configure an **IP reservation** on the **DHCP server**