
**Car Park:**
- What is SRC MAC and DST MAC? -> ==Source MAC and Destination MAC, used for local comms between devices on same segment, change at every router hop cuz router re-encapsulates packet in a new frame==
- DHCP only works for new devices on network or any device without IP? -> ==Works for all devices new or current when no IP address assigned==
- Subnetting improves only overall, individual or both network's security? -> ==Both==

**LAN Topologies**

Topology = Design/Layout of a network

Type of topology:

1. **Star:** 
- Devices connected via central networking device (e.g switch or hub)
- Most common today
- Info all sent to devices in topology goes through cnd it's connected to
- More scalable
- High cost (more cables and cnd)
- More maintenance needed
- Harder to troubleshoot at scale
- Breaks if cnd fails

2. **Bus:**
- Devices all connected along one cable called the backbone cable
- Devices branch off cable at different points (like leaves on a tree branch)
- More cost efficient (less cables no cnd)
- Easy set up
- All data travelling along same cable = prone to slowing and bottle necking if devices are requesting data at the same time
- Difficult to troubleshoot as all data travelling along same route
- One point of failure on backbone cable = if broken, devices cannot receive or transmit data along bus

3. **Ring/Token:**
- Devices connected directly to each other forming a loop
- Sends data around loop until target device is reached, using other devices along path to forward it
- Devices will only send the data if they don't currently have any data to send of their own, if they do they will send their own data first
- Less cabling and dedicated hardware dependence
- Less prone to bottlenecks as less traffic travelling at one time
- Easy to troubleshoot due to one data travel direction
- Inefficient, data needs to visit each device along the way to target
- One broken cable or device breaks whole network


**What is a Switch?**
- Connects devices to a network
- A device designed to gather many other devices on a network via Ethernet
- Gathered devices plug into the switch's port
- Typically used in larger networks where many devices need to be connected
- Can have ports of 4, 8, 16, 24, 32 and 64
- More efficient than hubs or repeaters as it just sends received packets to the target MAC addy (using its MAC table) instead of repeating every port as a hub does = lower network traffic.
- Tracks what device is connected to what port

**What is a Router?**

- Connects and passes data from one network to other networks via routing
- Routing involves creating path between networks so data can be delivered
- Useful when devices are connected by multiple paths

 ## **[[Subnetting]]**
- Splitting up a network into smaller networks within itself (e.g splitting up devices for departments in a business)
- Subnet mask = a number of 4 bytes representing how many hosts can fit within a network; looks similar to an IP addy 
- Use IP addies to:
-Identify network addy (Check subnet exists then find name/ID)
example address -> 192.168.1.0 <- Always uses 4 octets even if = 0
-Identify host addy (IP addy of device within network)
example host address -> 192.168.1.100 -> host portion = 0.0.0.100
-Identify default gateway (network entrance & exit usually a router, firewall or layer 3 switch)
example address -> 192.168.1.254 <- gateway portion = 0.0.0.254
- Default gateway = special address given to device on network that can send data to another network
- Subnetting:
1. Improves efficiency
2. Improves security
3. Gives full control over networks 
- Allows separation of networks to help improve security i.e. Separating free customer WiFi in store from the store's systems

**ARP**
- Allows devices to identify themselves on a network by associating their MAC addy with an IP addy on the network
- Each device on a network keep a log of the MAC addies associated with other devices
- Devices send a message to the entire network to find a specific device when they want to communicate.
- Devices can use ARP to find MAC addy of a device to communicate
- Identifiers = MAC and IP addies

**How does ARP work?**
- Devices store identifiers of other devices on the same network in a cache
- Maps identifiers using **ARP Request** and **ARP Reply** messages
- Once process is complete requesting devices memorises mapping and stores it on its ARP cache for future use => Makes future communication faster

**DHCP**

- Allows for automatic IP addy assigning to new device on a network
- Device sends a DHCP Discover request to see if any DHCP servers are on the network, only if not given an IP addy manually upon connecting
- Server replies with DHCP Offer to show an available IP addy
- Requesting device sends DHCP Request reply to say it wants the offered IP addy
- DHCP sends DHCP ACK reply to acknowledge assigning completion and device can start using given IP addy

## **Summary**
- **LAN** = Local Area Network = A network of devices connected together in a single physical location that is owned and managed by a single person or organisation
- **Topologies** = How devices on a network are connected, types are:
1. Star - Devices all connect to single networking device
- efficient and scalable
- high cost and difficult to maintain at scale

2. Bus - Devices connected together via one **backbone** cable
- devices branch off like leaves on tree branch 
- data travels left or right along cable to reach target device
- cost efficient, easy set up
- prone to slowing or bottlenecking, one break in backbone can break whole network

3. Ring/Token - Devices connected directly to each other like a ring 
- data sent through loop to reach target, 
- less prone to bottlenecking, cheaper as less cable + no need for dedicated network device, easy troubleshooting
- Inefficient + device won't forward data until has none to send first, one broken cable breaks whole network

- **Switch** - Connects devices to network via Ethernet cables plugged into its ports, used in larger networks. Sends received packets direct to target MAC addy (using MAC table) = lower network traffic, tracks devices connected to each port
- **Router** - Uses routing to connect networks, useful when devices connected by multiple paths
- **Subnetting** - Splitting up network into smaller networks within self, uses subnet masking. Improves efficiency & security while giving full control over the subnets. Uses IP addies to:
1. Identify network addy (Subnet existence then name/ID)
2. Identify host addy (IP of host device on subnet)
3. Identify default gateway (subnet entrance & exit for traffic)

- **ARP** - Maps Identifiers using ARP request and ARP reply messages so devices can find target on a network by finding its paired MAC addy and IP addy. Devices remember and store Identifiers of other devices on network on an ARP cache for future use
- **DHCP** - Allows for automatic IP addy assigning to devices on network, only works if DHCP server exists on network