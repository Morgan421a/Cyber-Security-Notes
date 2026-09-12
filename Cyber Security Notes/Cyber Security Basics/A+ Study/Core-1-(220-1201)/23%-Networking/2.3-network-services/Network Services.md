### DNS Server
- **Domain Name System**
	- Convert domain names to IP addresses and vice versa
- Multiple DNS servers running at the same time
	- Load balanced across many different servers based on the domain names the servers support 
		- e.g. One domain is supported by a group of DNS servers and when it is requested those servers are accessed or a cached version of the domain data from those servers
- Typically managed by the ISP or enterprise department
- Considered a critical resource

### DHCP Server
- **Dynamic Host Configuration Protocol**
- Automatic IP address configuration
- Very common service
	- Available on most home routers
- Enterprise DHCP usually has multiple servers for the sake of redundancy
	- If one server goes down, other DHCP servers can provide the service for devices on the network

### File Share
- Centralised storage of documents, spreadsheets, videos, pictures and other files
	- A **Fileshare**
- Can be used to share files with people both within and outside of an org
- Tend to be a standard system of file management
	- e.g. SMB Usually for Windows, Apple Filing Protocol (AFP) for macOS, etc.
- Front-end often hides the protocol being used
	- Users usually only see a file management front-end (copy, delete, rename, etc.)

### Print Server
- **Connects a printer to the network**
	- Provides printing services for all network devices
- Can be software within a computer
	- Computer is connected to the printer
- Can be built-in to the printer
	- Uses a network adapter and software (e.g. a network card in the printer)
- Uses standard printing protocols (often found in the manufacturer's guide book), some standard protocols are:
	- SMB (Server Message Block)
	- IPP (Internet Printing Protocol)
	- LPD (Line Printer Daemon)

### Mail Server
- **Used to send, receive and store emails**
- Servers can be:
	- In the cloud <- Usually managed by the ISP or Cloud Service Provider
	- Local within a data server <- Typically managed by the enterprise IT department
- Usually one of the most important services
	- High uptime expected with 24/7 support

### Syslog
- **Protocol used for message logging**
	- Works across a diverse range of systems
	- Consolidates logs into one central database
- Central server called a Security Information and Event Manager (SIEM) usually exists
	- Central consolidation point for all log files
	- Allows all logs to be put together even across diverse systems
- Requires a large amount of disk space
	- Lots of logs which are usually kept for a long time from many different systems

### Web Server
- **Responds to browser requests** using standard web browsing protocols (HTTP/HTTPS)
	- Web pages built with HTML (e.g. HTML5)
- Web pages stored on the server which are then accessed and interpreted by a web browser to present the requested page to a user
	- Downloaded to the browser
	- Pages can be static or built dynamically in real-time

### Authentication Server
- Sometimes called a Triple A (AAA) server
	- **AAA = Authentication, Authorisation, and Accounting Server**
- **Primary role to check username and passwords** then provide access to the requested services if authenticated successfully
- Typically uses a centralised database to allow for ease of administering all users on a network from one central point
- **Almost always used within enterprise networks**
	- Highest levels of security need to be provided such as ensuring each individual has their own set of credentials
- **Rarely seen/required on home networks**
- Often use a set of redundant servers
	- Ensures service is always available even if one of the servers fails/goes down
- **Extremely important service**

### Database Server
- **Store data on database tables**
	- Information saved into **columns** and **rows** similar to a spreadsheet
- Allow for **tables** to be **linked** together to form a **Relational Database**
	- Links between the tables are the relationships
	- Allows for data to be linked together providing a **faster** and more **flexible** method of data storage (e.g. easier to find desired data in large database)
- **Structured Query Language (SQL)**
	- A Language **used** to **store** and **retrieve** data from a database
	- Found in many popular database servers such as **Microsoft SQL Server**, **MySQL**, etc.

### NTP Server
- **Network Time Protocol**
- High importance, time used for various reasons on a network, such as:
	- Encryption, Logins, Backups, Log Timestamps
		- Some encryption technologies require all systems to be running with the correct date and time
- Typically **one or multiple NTP Servers** running which reference a **central clock** to ensure all of them have the correct date and time
	- Responds to time requests from **NTP Clients**
- Local Computers use an **NTP Client**:
	- Configured to access particular **NTP Server** and periodically request time updates from it
	- Daily Sync is common

### Spam Gateways
- Spam gateway **evaluates incoming emails** to determine which are legitimate or which are spam
- Usually a separate service, can be cloud-based or run on an on-site server
- Not perfect, sometimes flags legitimate emails as spam
	- Reason behind some legitimate emails ending up in the spam fold

![[Pasted image 20260822133453.png]]

### All-in-one Security Appliance
- **Placed on the outside of an org's network between them and the Internet**
- Referred to as:
	- Next-generation firewall
	- Unified Threat Management (UTM)
	- Web Security Gateway
- **Many Functions combined into a single device**, some potential functions are:
	- URL Filtering / Content Inspection
	- Malware Inspection (e.g. within emails or real-time network traffic)
	- Built-in Spam Filter
	- CSU (Channel Service Unit)/DSU (Data Service Unit) 
		- Digital interface device used to connect data terminal equipment (DTE) such as a router, to a dedicated digital circuit such as a T1 or T3 line
			- Used for connecting to older wide area network connections
	- Router, Switch interfaces
	- Firewall Functionality
	- IDS/IPS Functionality
	- Bandwidth Shaper
		- Used to minimise the impact of certain apps on the network
	- VPN Endpoint/Functionality
		- Allows for secure connection to other sites or allow end users to connect directly to the All-in-one Appliance over a secure channel

### Load Balancers
- Helps orgs maintain smooth, reliable running of apps and services
- **Connect multiple devices at the same time and share the "load" (traffic) across those devices**
	- Utilise multiple servers
	- Invisible to the end-user
- Large Scale implementations such as a web server or database farm within an organisation
	- Servers connected to a Load balancer which helps by distributing the incoming requests across the many servers within said farm
- Have fault tolerance
	- Automatically knows if one of the servers has failed (stopped communicating) and stops forwarding requests to that particular server
		- Gives technicians time to evaluate, resolve issues, and connect the server back to the load balancer which then automatically knows it's available again and can be sent requests
		- Process happens quickly, such that end-users won't even realise an outage occurred
	- Server outages have no effect
	- Fast convergence

### Proxy Server
- An **intermediate server** used by some orgs **through which:**
	1. A client makes a request to the proxy
	2. The proxy performs the actual request on behalf of the client to the service
	3. Proxy receives the response from the service and evaluates it
	4. If everything within the response is appropriate and secure, the proxy forwards the response back to the end-user
- **Primarily used as a security tool**, but can also be used for:
	- Access Control
	- Caching
	- URL Filtering
	- Content Scanning (limiting what data can be received through the proxy server)
- Typically sits invisibly in the network
	- End-user has no idea the proxy exists and is analysing their device's incoming and outgoing traffic

### SCADA / ICS
- **Supervisory Control and Data Acquisition System** / **Industrial Control System**
- **PC/Systems used to manage industrial/critical infrastructure** such as:
	- Power Generation, Refining, Manufacturing Equipment, etc.
- Used within industries such as:
	- Facilities, Industrial, Energy, Logistics, etc.
- Specialised system that allows for the remote viewing, managing, controlling, and maintaining of systems (e.g. traffic lights) across an entire network
- Distributed Control Systems (DCS)
	- Control spread out across many controllers often physically near the equipment they manage
	- Real-time information
		- Data continuously updated
	- System Control
		- Operators (or automated logic) can send commands back down to the equipment such as: open a valve, shut off a pump, etc. <- based on what the real-time data is showing
- **Highly valuable and often crucial systems** which require extensive **segmentation of the networks**
	- Typically isolated from the main network
	- No access from the outside
	- Some only available by physically visiting a particular part of the network or accessing it through a very controlled system

### Legacy and Embedded Systems
- **Legacy Systems = Old system**
	- Old doesn't mean it's not important, sometimes they're very important which could be the reason behind not modernising them
	- Learning and understanding the legacy systems can be just as important as the current/newer systems
- **Embedded Systems**
	- **Purpose Built Device**
	- Users typically don't have direct access to the OS running on the embedded system
	- Examples include: Alarm system, door security, time card system, etc.
		- Daily interaction without interacting with the device OS itself
	- Manufacturer usually needs to provide the tools needed to support the equipment
		- Typically don't require much ongoing maintenance

### IoT (Internet of Things) devices
- Appliances e.g. refrigerators
- Smart devices e.g. Smart speakers that respond to voice commands
- Air control e.g. Thermostats, temperature control
- Access e.g. Smart doorbells, doors and windows
- May require a **segmented network** to **limit access** in the event that someone gains access to an IoT device