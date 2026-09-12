- Many different devices, all having different roles
- Some functions are combined together
	- e.g wireless router/switch/firewall

### Routers
- **Routes** traffic between **IP subnets**
- Makes forwarding decisions based on **destination IP address**
- Routers can exist within switches, often called a **"Layer 3 Switch"**
- Often connect diverse network types such as LAN, WAN, copper, fibre, etc.

### Switches
- Used to **connect end devices** (essentially bridging hardware) and **forward data** based on the destination **MAC address**
- Often **very quick** due to the switching occurring **within** the **hardware** itself
	- Hardware used is often an **Application-specific integrated circuit (ASIC)**
- Typically have many **ports** (aka **interfaces**) e.g. 24, 48, or even hundreds of port switches
- May provide **Power over Ethernet (PoE)** <- Both powers devices and allows for data transfer
- Layer 3, aka **Multilayer switches**, **routing functionality** <- more than just layer 3 multilayer switches exist offering different functionalities
##### Unmanaged Switches
- Very few config options
- Effectively just a "plug and play" device
- Fixed configuration
	- e.g. No VLANs
- Very little integration with other devices
	- e.g. No management protocols, no log storage, etc.
- Lower price point due to simplicity
##### Managed Switches
- Often **larger** than unmanaged switches
- Typically have **VLAN functionality**
	- Interconnect with other switches via **802.1Q**
- May allow for **traffic prioritisation**
	- e.g. web traffic gets a higher priority
- Can have **redundancy support**
	- Maintains uptime if a switch on the same network fails including itself, other switches or the switch itself can carry the additional load
- Many switches also allow for **port mirroring**
	-  **port mirroring** = Plug in a security device to an interface and redirect/mirror traffic from one interface to the monitoring device
- Often allow for **External Management**
	- Can be done via protocols such as the **Simple Network Management Protocol (SMNP)**

### Access Point
- Allow **devices** to **connect** to a **network** over a **wireless connection**
- **Not a wireless router**
	- **Wireless Router** = A **router** **and** an **access point** in a single device
- **Access point** is a **bridge** (**bridged communication**)
	- No translation of IP addresses, no routing takes place
	- Effectively just **switching** **between** a **wireless** network **and** a **wired** network
	- **Extends** the **wired** network **onto** the **wireless** network
	- Makes **forwarding** **decisions** based on the destination **MAC address**
		- e.g. access point evaluates a frame and decides if it should be forwarded via the wireless network or the wired network

### Cable Infrastructure
- Using desks within a corporate network as an example:
	- Each desk likely connected back to a central closet via an **Ethernet cable**
	- Each cable likely **terminated** within said closet onto a **punch-down block** typically built into the rear of a **punch-down patch panel**
	- Allows cable to be run from the desk to the closet and lock everything down onto the punch-down block
		- Simplifies cable management <- cable between desk and closet will never move
	- Opposite side of the **patch panel** may have **RJ45** connectors to allow for cables to be moved as needed
		- e.g. plugging into a different switch via the **RJ45** connectors on the patch panel <- cable between desk and punch-down block stays in place, only plugged in location on rear of the patch panel changes
### Patch Panels
- Combination of **punch-down blocks** and **RJ-45** Connectors
- Runs from desk are made once
	- Permanently punched down to patch panel
- **Patch panel** to switch can be easily changed
	- No need for special tools
	- Just use the existing cables
- Example:
- ![[Pasted image 20260826070242.png]]
- Top, numbered row = Rear of punch-down patch panel, cables likely terminated on other side running from desks
- Bottom row = Switch, if needing to move the connection, only the RJ-45 connector at the bottom needs to be moved

### Firewalls
- **Filters traffic by port number**
	- **OSI Layer 4 (TCP/UDP)**
	- Compares port number to set of **access lists** inside of the firewall that determines whether the traffic is allowed/disallowed
- Some firewalls can **filter based** on the **application** (next-generation firewalls)
	- e.g. Allows web traffic to traverse the firewall but block any type of remote access software
- Many firewalls can be used as a **VPN Concentrator** <- Can **encrypt traffic** into/out of the network
	- Protects traffic between sites
- Some firewalls can act as a **proxy**
	- A common security Technique
- Most firewalls can be **layer 3 devices (routers)**
	- Usually sits on the ingress/egress (inbound/outbound) of the network

### Power Over Ethernet (PoE)
- Providing **both** **power** and **data** over the **same Ethernet connection**
	- **One wire** for both **network** and **electricity**
- Often used for desk phones, cameras, wireless access points, etc.
- Useful in difficult-to-power areas
- **Power provided at the switch**
	- **Built-in** power - **Endspans**
	- **In-line** power injector - **Midspans** <- Used when switch doesn't support PoE
##### PoE Switch
- **Power Over Ethernet** -> **IEEE 802.3**
	- Commonly marked on the switch or interfaces as such:
		 ![[Pasted image 20260826071512.png]]
##### PoE, PoE+, PoE++
- Switch documentation should specify what type of PoE is supported
- **PoE** -> **IEEE 802.3af**
	- Original PoE specification
	- **15.4W DC power, 350 mA max current**
		- **Up to 15.4W** delivered at the **switch**
		- ~**12.95W** at the **device**
	- Useful for powering low-power devices such as basic IP phones, wireless access points, standard security cameras, etc.
- **PoE+** -> **IEEE 802.3at**
	- **25.5W DC power, 600 mA max current**
		- **Up to 30W** at the **switch**
		- **~25.5W** at the **device**
	- Useful for larger devices tat require a bit more power than PoE provides
		- e.g. PTZ (Pan-Tilt-Zoom) Cameras, high performance access points, etc.
- **PoE++** -> **IEEE 802.3bt**
	- **51W (Type 3), 600 mA max current**
		- **Up to 60W** at the **switch**
		- **~51W** at the **device**
	- **71.3W (Type 4), 960 mA max current**
		- **Up to 90W-100W** at the **switch**
		- **~71W-90W** at the **device** <- Used for laptops, digital signage, building management systems, etc.
	- Version Introduced with 10 Gig Ethernet (10GBASE-T) running over copper cables
- PoE standards are **downward compatible**, not upwards though
	- Compare the device with the switch support
	- Poe+ won't power a PoE++ device

### Cable Modem
- Typically used where internet connection is provided by a cable television provider
- Uses a **Broadband** connection, often provided over a **coaxial (coax) cable**
	- Provides an ethernet connection on the other side
- Able to connect to the same network that sends television signals and send data across the same line
- Transmission across multiple frequencies
- Different traffic types
- Sometimes referred to as a **DOCSIS** device
- Data on the "cable" network
	- **Data Over Cable Service Interface Specification (DOCSIS)**
		- Standard used to transmit the signal across the cable network
- **High speed networking**
	- Speeds up to **1 Gigabit/s are common**
- Multiple services
	- Data, voice, video
- Due to high throughput over the connections, can commonly be seen in corporate environments too
- Operates on a **Shared Bandwidth** model
	- Multiple households in a neighbourhood share the same coax cable infrastructure and available data channels
### DSL Modem
- **Digital Subscriber Line (DSL)**
- Uses **Telephone Lines**
- Utilises **same wires** used by an **analog telephone**, but also sends **digital signals** at the same time
- Can provide decent throughput
- **Download speed faster than upload speed (asymmetric)**
	- **200 Mbit/s downstream / 20 Mbit/s upstream are common**
		- **Downstream** = Data flow from internet/ISP toward a device, corresponds to downloading files, streaming video, loading web pages, etc.
		- **Upstream** = Data from a device toward the internet, corresponds to uploading emails, posting on social media, video calling, etc.
- **Throughput** **affected** by **distance** from the **Central Office (CO)**
	- **Central Office** = A specific physical locations (a telephone company building) that sits between a DSL modem's location and the ISP's core network
	- Approximately **~10,000 foot (~3000 m) limitation** from the **Central Office (CO)**
	- Faster speeds may be possible if closer to the **CO**
- Uses **Twisted-pair copper cabling**
- Operates on a **Dedicated Bandwidth** model
	- Copper line not shared with neighbours, ensuring consistent bandwidth and speeds regardless of local network congestion

### ONT
- **Optical Network Terminal (ONT)**
- Used to **convert fibre** going into homes/businesses **into copper connections** to be used in a traditional network
	- Connect the **ISP fibre network** to the **copper network**
- **ONT** device usually in a central place or a **Demarcation point (demarc)**
	- Can be: Within the data centre itself, in a terminal box that's outside or just inside the building
- Referred to as the **demarcation point** because it's where the **determination** regarding what part of the network is the **User's responsibility** and what part is the **Service Provider's responsibility**
	- One side of the box is the ISP <- problems outside the building (external fibre cable and the ONT itself) are the ISP's responsibility
	- Other side of the box is the User's network <- problems inside the building (internal wiring, sockets, cabling within property, etc.) are the User's/developer's responsibility
- Example of an ONT:
	![[Pasted image 20260826075232.png]]

	- Large black cable on left = Fibre connection on the ONT
	- Right side in this example has RJ-11 connections that can be used for voice communication, likely Voice Over IP (VOIP) that has phone numbers associated with it 
	- Middle in this example has an RJ-45 connection for Data, likely outputting an Ethernet link which can be plugged into a router
	- Top right brass threaded connector = F Connector that can have a coaxial RF connector plugged into it to be used for video by connecting it to a cable box or directly to a television

### Network Interface Card (NIC)
- Used to **connect devices or servers** directly **to** the **Ethernet network**
- Every device on the network has a **NIC**
	- Computers, servers, printers, routers, switches, phones, tablets, cameras, etc.
- Many different types that are specific to the network type, such as:
	- 100 Mbit/s Ethernet, Gigabit Ethernet (GBe) over copper, WAN, Wireless, etc.
- Often built-in to the motherboard
	- Can be added as an expansion card if mobo doesn't have one built-in or even if more Ethernet interfaces are needed
- **Contains the hardware address**
	- **Media Access Control (MAC) Address**
		- Allows for each individual interface to be referenced across the network (each interface has its own MAC address)
- Some Network Interface Cards allow for **Wake-on-LAN (WoL)**:
	- A feature that allows for a computer to be remotely powered on by sending a special network packet, even if the device is fully shut down
		- Has to be enabled in BIOS/UEFI
		- Only works reliably on wired ethernet connections
		- Doesn't work across the internet by default, reaching a machine remotely typically requires port forwarding or being on a VPN into the device's LAN first
