**Car Park**

**Virtualisation**
- Allows multiple applications to share a single server using a [[Virtualisation]] layer called a Hypervisor which acts like a referee between lab machines, enabling each virtual computer to act independently
- Virtualisation:
	- Reduces costs by reducing the required number of servers for an organisation
	- Ensures servers aren't being under-utilised i.e the only application on a server using only 5% - 20% of the server's resources
	- Reduces deployment time; since less servers are needed the time that would've been spent building more had virtualisation not been implemented can be used elsewhere
	- Easier to scale by allowing resources to be dynamically adjusted without the need for physical intervention through Vertical Scaling, Horizontal Scaling and Live Migration
- Each virtual computer, called a lab machine or a VM acts as an independent system within its own OS, apps and settings despite sharing the same physical hardware underneath.
- Key benefits of Virtualisation include:
	- Cost saving
	- More efficient resource usage
	- Safe testing for cyber security
	- Faster deployment
	- Flexibility
	- Portability
	- Scalability
	- Centralised Management

**Virtualisation Components**
- **Hypervisor** = The software used to create and manage VMs, it:
	- Divides a physical computer into multiple virtual ones
	- Gives each VM its own share of resources (CPU, memory, storage)
	- Keeps everything isolated and safe
	- Manages VM lifecycle (start, stop, pause, clone, delete)
- Hypervisors -> two main types of implementation each suited for specific scenarios as well as better/best use cases for each:
	1. **Type 1** = Runs directly on physical hardware, faster, more efficient and better for servers/professional environments. Best used for:
		- Production Servers
		- Database Servers
		- Data Centres
	
	2.  **Type 2** = Runs within existing OS, easier to install, better for learning, testing or small setups. Best used for:
		- Testing Malicious Files
		- Software Testing
		- Kali Linux
	- Either type can be used for all tasks mentioned but each are better/safer to use for their listed ones

- *Care must be taken when testing malicious files using virtualisation to prevent malware from infecting host machine. 
	- *One method to prevent this is to use different OS's for host and guest machines*
	- *Another way is to isolate guest machine so it doesn't communicate with the host*

- **Lab Machine (VM)** = Virtual computer created by the hypervisor, behaves as a real machine:
	- Has own virtual resources (CPU, RAM, Storage and Network)
	- Can run any OS
	- Completely isolated from other VMs -> if one breaks others will continue to work

- VMs can be used to work on a different OS without the need to setup dual booting or getting a new system as well as testing if a file is malicious by setting up an isolated lab machine to protect main computer from infection
- **Oracle VirtualBox** and **VMware Workstation** = software that act as a type 2 hypervisor, allowing for deployment of VMs on a computer

- **[[Container]]** = Isolated environment which runs a single app and all necessary components to support it.
	- Borrows core of existing system by running on Kernel
	- Start quickly
	- Use less resources than full VMs -> They're lightweight
	- They have to match the host's system type i.e windows container can't be run on linux machine

- Act like small-self contained spaces because they:
	- Package app and its dependencies
	- Share host's OS so can start almost instantly
	- Remain isolated from each other so a container behaving incorrectly doesn't affect others
	- Can run consistently on any machine -> good for development, testing and scalable deployments

- Easy to deploy in a VM using Docker
	- Uses container images to simplify the setup of containers
	- Network Ports **must** be mapped during configuration to allow network traffic to reach applications i.e. 80 <- HTTP, 443 <- HTTPS, 8080 <- common alternative for web servers or when port 80 is in use
