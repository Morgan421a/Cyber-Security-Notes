- **Computer hardware components:**
	- **CPU** - Executes instructions and calculations <- More **cores** = more parallel processing
		- Connect via **CPU slot** on mobo
	- **GPU** - Translates data from OS, apps and other components into visual data on a monitor/screen
		- Connect via **PCI-Express** (PCI-E) slot on mobo
	- **PSU** - Supplies other components with power
		- Connects to other components via **molex cables** or **mobo**
	- **RAM** - temporarily stores data for calculations/instructions being carried out by CPU. Data lost on power off 
		- Connect via RAM slots on mobo called **DIMM** slots
	- **Networking Card** - NIC, grants device networking capabilities. 
		- Often built into mobo but can be added as expansion card via **PCI-E** slots on mobo
	- **Storage (HDD/SSD)** - Long term data storage, data not lost on power off. HDD - mechanical, uses spinning disc, slower but cheaper. SSD - No moving parts, uses chips for data storage and reading, faster but more expensive
		- Connect internally or externally via **SATA** cables or via **PCI-E** slots on mobo
	- **Motherboard** - What most other components sit on. Uses **copper traces** to transport power to components not connected to PSU directly i.e. RAM
	- **Input/Output (I/O) Devices** - Used to provide and receive data. Input = mouse, keyboard, microphone. Output = printer, headphones, monitor
		- Plug in to mobo's rear **I/O panel** typically using USB, HDMI, Display port

- **Computer Power on process:**
	1. Power button pressed, sends signal to PSU to allow power to flow to components.
	2. **Unified Extensible Firmware Interface (UEFI)**/**Basic Input Output System (BIOS)** starts up which allows other components to start.
		- **BIOS** similar to **UEFI** but has been mostly replaced by **UEFI**
	3. **UEFI** runs checks on all components to make sure they're present, running and functioning correctly
	4. **UEFI** looks through configured priority list of boot drives to find where to initiate the boot up routine for the OS is
	5. **Bootloader** initiates and moves the OS to the RAM for startup after which **UEFI** hands control of components over to the OS

- **Some Computer types:**
	- **Laptop** - Small, portable, weaker than desktop and prone to overheating. 
		- Good for working from anywhere. 
		- Not great for intensive tasks or those needing consistent performance 
	- **Desktop** - Fixed, more powerful than laptop with better cooling.
		- Good for more intensive/performance based tasks
		- Less accurate and worse performance than workstation
	- **Workstation** - Fixed, more powerful than desktop thanks to extra hardware.
		- Good for highly intensive tasks or those where accuracy is needed
		- Expensive and take longer to setup than laptop or desktop + needs more space
	- **Server** - Fixed, Good for running apps/services/databases
		- Can handle many incoming requests and use virtualisation to run multiple servers on one physical server
		- Use backup servers and disks as fail-overs in case one breaks so services can keep running
		- Expensive, more difficult to learn and configure than previous examples, often lack a user interface
	- **Smartphone** - Small, portable, optimised for battery life and performance
		- Good for day to day use and communication
		- Limited options for tasks, not as powerful as tablets
	- **Tablet**- Larger, portable version of smartphone often optimised more for towards performance than battery life
		- Better for more intensive tasks or those where a larger screen is beneficial i.e. Art
		- Still limited on available tasks, not quite as easily portable as smartphones
	- **Embedded Computer** - Built into devices to execute code i.e. coffee machine controller. Can be network connected but typically isn't
		- Allows for devices to remain small while still running code and not hinge on a working network (assuming not needing to be connected)
		- Depending on size/power will be limited to what code/how much code it can run
	- **Internet of Things Device** - Built into single purpose devices to allow them to send and retrieve data over the internet i.e. Smart doorbell or thermostat
		- Allow devices to remain small while still having internet connectivity capabilities (though only for one purpose)
		- Devices often hinge on maintaining internet connection to function properly
	- *IoT and Embedded are similar but IoT devices will always connect to the internet. Embedded computers often aren't network connected but they can be, however they can't connect to the internet.*
	  - *IoT and embedded computers are more so a role definition as opposed to a device/computer definition. They're purpose built for each individual device so design and purpose between their devices will change*

- Different computer types exist due to each being better than the others in some aspects but having to make trade-offs in order to do so, for example:
	- Laptops = Small and portable, allowing work from anywhere unlike desktops which are fixed. However laptops are less powerful and prone to overheating due to smaller and often weaker components as well as a smaller, less thorough cooling system

- **Protocol** - A system, typically on a server, that defines a set of rules for communication between devices i.e. HTTP, TCP, FTP
	- **Protocols define 5 things:**
		- The commands that both the client and server understand
		- The syntax that both the server and client must use
		- How requests from the client should be structured
		- How a server responds to valid requests
		- How a server responds to faulty/invalid requests

- **Port** - The point on a device through which data is sent and received, can be **0 - 65535**, though most commonly will be **0 - 1024**
	- In servers it is also used to identify specific services/apps to help deliver requests and responses to and from the correct one
		- *Often worded as the port upon which the service/app is "listening" on*
	- Standard ports streamline communication across apps/services by allowing them to follow simple rules for data transmission (both ways) creating a sense of order across the internet and networks

- **Client-Server Process:**
	1. Client makes a request to a server via the same port that the service is "listening" on, using the rules of structure, syntax and commands set out by the protocol
	2. Server receives the request via the corresponding port to a service and, if valid, processes a response based on the rules laid out by the protocol i.e. sends data for an HTTP GET request
	3. Server sends response back from the service's port to the corresponding client port using the same syntax and commands outlined by the protocol
	4. Client receives the response

- **HTTP(S)** - Protocol used for client-server web communication.
	- **Stateless** = Doesn't "remember" previous requests and responses, treats each one as its own individual pair.
		- **Pseudo-Statefulness** can be created by utilising **cookies** to store **session IDs** for users or login credentials such that a user's site specific data (i.e site settings or shopping cart) can be added to a response, removing the need for users to start from scratch on a website they've used before
			- **Session IDs** - Stored on the **client's browser** in a **cookie** which is sent with each request, via headers, to the **server** which stores the session data for the matching ID

- **HTTP 9 core methods:**
	- **GET** - Requests data from web server
	- **HEAD** - Similar to GET, but requests only headers from web server without the body
	- **PUT** - Fully modifies (overwrites) the data of an existing record on web server, can create new records
	- **POST** - Used to create new records on web server, cannot modify existing ones
	- **PATCH** - Partially modifies data, changing only the specified fields, cannot create new records
	- **DELETE** - Used to remove records from web server
	- **CONNECT** - Used to create a connection between the server and client device called a tunnel ==(**Not** the same as a VPN tunnel)==
		- **Tunnel is not encrypted by default**, **Transport Level Security (TLS/SSL)** must be used in conjunction with HTTP to encrypt data travelling within it
	- **TRACE** - Echoes requests back to the client, used for diagnostic analysis
	- **OPTIONS** - Shows available list of methods for an app/service on the web server

- **Virtual hosts** - Allow for multiple apps/services to be run on the same physical server while keeping them isolated from each other
	- Allows a single physical web server process (listening on just port 80 or 443) to **host multiple different websites** simultaneously on the one port 
	- **Limits** = hardware resources, **non-distinct web services** (like DBs or game servers) still need unique ports unless routed through a **reverse proxy** <- *External research/context*

- **Virtualisation** - The act of creating **virtual machines** by splitting up a physical host machine's hardware resources into virtual resources to be used by hosted VMs such that they can act like their own complete and individual computer.
	- **Virtual resources** in the VM context = CPU, RAM, Storage, Network
	- **Benefits:**
		- Allow for multiple machines to be run on a single physical device without needing to by more hardware <- reduces costs
		- Enables the use of different OS's from the host machine without needing to build a whole new physical device <- reduces costs and setup time
		- Also allows for:
			- **Vertical scaling** - Adjusting resources to a VM to meet its current demands
			- **Horizontal scaling** - Cloning and deploying multiple VMs to spread traffic across a cluster of virtual computers/servers
			- **Live migration** - Moving a running VM to a different physical host machine without stopping it or interrupting its processes, good for maintenance or troubleshooting
- **Hypervisors** - The **software** used to: 
- Create and deploy VMs
- Manage the **VM lifecycle** (start, stop, clone, delete)
- Manage the VMs and their resources - Allowing for resource elasticity, resources can be increased or decreased as needed for each VM
- Keeping VMs isolated from each other and the host machine which helps improve security and stability (if one machine breaks/behaves poorly the other are unaffected)

- Two types of Hypervisors exist, both can be used for every purpose but each excel in some areas in comparison:
	- **Type 1**: Run on the host machine's hardware (**Bare Metal**), Hypervisor sits between the **kernel** and the VMs
		- Faster than type 2 but more difficult to setup and configure
		- Better for servers or databases due to being faster improving read and response speed for requests
	- **Type 2**: Run on **existing OS's** using **software** such as **Oracle VirtualBox** or **VMware Workstation**, Hypervisor sits between the host machine's OS and the VMs
		- Easy to setup, install and configure but not as fast as type 1
		- Better for learning, development and malware analysis

- **Malware analysis using VMs** - Good way to analyse malware by running it on a separate "not real" machine though care must be taken to prevent **VM escape** (host machine infection). Two possible safety measures are:
	- Completely **isolating** the VM from the host machine and its network such that they **cannot communicate** with each other, neither can the VM communicate with other devices on the network
	- Running the VM on a **different OS to the host machine** such that the different **architecture/binary incompatibility** between OS's prevent malware that does escape from working as it would on its target OS -> [[Malware VM Escape|Advanced Malware can get around this]]

- **Containers** - Single, isolated instance of an application created using virtualisation which borrows its core for the host machine's kernel
	- Runs both the **app** and its **necessary components**
	- Can be used to run multiple applications on the same host machine while keeping them isolated from each other
	- Lightweight - resource drain is negligible compared to a VM
	- **Network Ports must be mapped during config** to create routes for external data to reach the app inside the container
	- Due to sharing sharing host machine's kernel they must be run on the same OS <- **different OS = different kernel**

- **Docker** - **Software** used to simplify the creation and configuration of containers through the use of **container images**.
	- **Container images** = Pre-configured containers designed to run specific apps, typically with their **dependencies** already installed.

- **Cloud** - Service which allows clients to run apps/services on a cloud provider's physical servers over the internet in the form of **cloud virtual computers/servers**
	- Have many benefits including:
		- **Pay for what you use** - Clients only need to pay for the resources they actually use from the provider. 
			- Removes upfront hardware costs and the potential for the under-utilisation of purchased resources
		- **Scalability** - Resources can be increased or decreased for virtual computers in order to meet demand
			- Can be changed on the spot as demand does and removes the need to wait for physical hardware adjustments
		- **On-demand-self-service** - Allows clients to add, change or remove their virtual computers on the cloud server without needing to wait for physical hardware
			- Increases efficiency for clients and allows them to still control their machines as they want to
		- **Security** - Improves security by adding an extra layer, being the cloud provider's own security infrastructure
			- Reduces risk of being attacked and increases ability to fend of attacks should one occur
		- **Global availability** - Available across the globe at any time
			- Allows users or clients on opposite sides of the world to interact and use the same application
		- **Stability** - If one of the hosted app/services breaks or goes down the other will remain unaffected and can run like normal
			- Provides peace of mind to clients regarding the stability of their service/app on a cloud server


- **VM vs virtual computer:** 
	- **Virtual computer** is a VM which runs using another physical computer's resources over the internet. 
	- A **VM** is the technology upon which virtual computers are built

- Cloud deployment types:
	- **Public Cloud** - Good for, websites and public apps/services, 
		- Most common and cheapest 
		- Allows for easy scaling of **public resources** to meet shifting demand
		- Best option in any scenario where private data doesn't exist
	- **Private Cloud** - Good for, healthcare and government services, or where any **private data** is involved. 
		- Provides greater customisation, compliance and control for sensitive data.
	- **Hybrid cloud** - Good for e-commerce or where both **private and public data** is used.
		- Allows for private data to be kept protected and away from public users
		- Still allows for scaling of public resources to meet shifting demand

- Cloud service types:
	- **Infrastructure as a Service (IaaS)** - Cloud provider only gives the resources, client responsible for the OS and application
	- **Platform as a Service (PaaS)** - Cloud provider gives resources and handles the OS/infrastructure, client only responsible for the application
	- **Software as a Service (SaaS)** - Cloud provider gives access to their own application so clients may access and use its features over the internet. i.e. Gmail or Zoom

- Cloud Providers:
	- **Amazon Web Services (AWS)** <- Most popular due to wide range of features and flexibility, attractive choice for individuals all the way up to large orgs
	- **Microsoft Azure** <- closest competitor to AWS
	- **Alibaba cloud** <- Very popular in Asia
	- **Google Cloud Platform (GCP)** <- Greater focus on AI, machine learning and data analytics tools
	- **Oracle cloud** <- Focus on enterprise apps and databases
	- **IBM cloud** <- Focuses on hybrid cloud and AI solutions for organisations

- AWS cloud servers example:
	- **EC2** refers to a virtual computer/server running on their cloud, each EC2 has its own virtual resources
	- Use **tags** (e.g. t2 (now legacy*), t3, m5 etc.) to denote the power and cost of a specific EC2 <- **Higher Value = More Powerful + Higher Cost**
		- * = *External research/context*