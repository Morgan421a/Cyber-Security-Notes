### The Hypervisor
- **Software that manages Virtual Machines**
	- Both the virtual platforms and the guest OS
- Can run on most systems
- May require a CPU that supports virtualisation
- **Modern Hypervisors** can be **used in conjunction with CPUs** **designed** specifically **with** **virtualisation in mind**
	- Can improve performance
- **Hypervisor** can **manage** **hardware** **and** **resources** such as CPU, Memory, Networking, Security, etc.
### Hypervisor Types
- **Type 1: Bare Metal**
	- **Hypervisor sits directly on top of a system's hardware**
	- **Bare metal** because no OS at the lowest level
		- **Hypervisor IS** effectively the **primary operating system**
	- **Example Type 1's**:
		- VMware ESXi, Microsoft Hyper-V, Xen Project
- **Type 2: Hosted**
	- **Hypervisor runs in existing OS using hypervisor software**
	- VMs run on top of current OS
	- **Example Type 2 software**:
		- VMware Player, Oracle VirtualBox, Parallels Desktop

### Virtualisation
- Hypervisor Sits between Hardware and VMs (Type 1/Bare Metal Hypervisor)
- Each app instance has its own operating system
	- Adds significant overhead and complexity each time a new VM is started
	- Virtualisation is relatively expensive

### Resource Requirements
- **Some CPUs designed to run in a virtual environment**
	- **Intel** -> Virtualisation Technology (VT)
	- **AMD** -> AMD-V
- **Hypervisor allocates memory to each VM**
	- **Uses** parts of **physical** system **memory**
		- System needs enough RAM to support the different VMs running simultaneously
- **Each VM has** its **own installed OS** **requiring disk space to store** both the **OS and** its **data**
	- Each **guest OS has** its **own** **image**
- **User** has **control** **over** **how** a **VM** can **interact** **with** a **network**
	- e.g. full internet connectivity or completely isolated from any networks
	- Configurable on each guest OS

### Network Requirements
- Most **client-side VM managers** **have** their **own** **virtual networks** **configured** **internally** **on** the **system**
- Some Hypervisors configure **Shared Network Address**
	- **VM** shares **same IP address as physical host** 
		- **Outside** of **VM**: 
			- VM can send out data to network and receive responses to its own requests
			- Can't receive unsolicited inbound connections from external sources without **port forwarding**
	- **VM** uses a **private IP address internally** 
		- **Inside** of **VM**: 
			- Allows physical host to communicate with the VM 
			- Gives VM a normal looking address internally
			- **VM cannot be seen on physical network**
	- Uses **NAT** to convert to the physical host IP
- **Bridged Network Address** 
	- Allows **VM** to **appear** **and** **act** **as** a **device** **on** the **physical network**
- **Private Address**
	- VM doesn't communicate outside of the virtual network

### Hypervisor Security
- **VM Escape**:
	- **Malware recognises** it's on a **VM** and **uses** a **flaw** **in** the **hypervisor** **to** **compromise** said **hypervisor**
		- Allows **malware** to **jump** **from VM's isolation to reach the hypervisor or host system**
		- **Focuses on accessing hypervisor or host OS**
		- **Prevent by**:
			- Keeping guest OS, host OS, and hypervisor patched and updated
			- Use secure configs for hypervisor and VMs
- **VM Hopping**:
	- **Malware** **moves from one VM to another** **on** the the **same host** by **exploiting** **hypervisor vulnerabilities or misconfigs** to bypass isolation
	- **Focuses on moving between VMs**
	- **Prevent by**: 
		- Updating and patching hypervisor
		- Following best practices for securely configuring guest OS and hypervisor
- Many hosted services are virtual environments <- Malware on one customer's server can reach out and control or access data on another customer's server
- **Live Migrations**:
	- **VMs** can be **moved between hosts over** a **network** **without** being **powered off**
	- **Risks** **data exposure during unencrypted migration** and **integrity compromise through on-path attacks**
	- **Prevent by**:
		- Encrypting VM images prior to migration
		- Ensure migration occurs only over trusted and secure networks
- **Data Remnants**:
	- **Residual data left after VMs are deprovisioned**
	- **Risks unauthorised access to sensitive data**
	- **Prevent by**: 
		- Encrypting VM storage locations
		- Destroying encryption keys when decommissioning VMs
- **VM Sprawl**:
	- **Uncontrolled deployment of VMs without proper management**
	- **Risks** a **lack of security updates** and **anti-malware on rogue VMs**; **increases vulnerability to attacks**, including VM escapes or hopping
	- **Prevent by**:
		- Enforcing changes control processes
		- Regularly auditing and managing VM deployments
- **Sandbox Escapes**:
	- **Attacker gets around sandbox protections to access privileged systems**
	- **Prevent by**:
		- Keeping software and OS updated
		- Using strong endpoint protection solutions
		- Limiting browser extensions and add-ons
### Guest OS Security
- **Every VM** is **a** **self-contained OS** akin to a real computer
	- VM security should be configured as if it's an actual desktop/server
- Use **traditional security tools** such as **Host-based firewalls**, **Anti-virus**, **anti-spyware**, etc.
- **Be aware of rogue VMs**
	- Attackers publish their own **VM with malware embedded**
		- Once VM run, OS already infected with malware
- **Self-contained VMs provided by 3rd parties can be dangerous**
	- Ensure knowledge of all services running on third party VM prior to installing and running

### Virtual Desktop Infrastructure (VDI)
- **Desktop runs as a VM** **on** a **separate device**, typically **across** the **network** **or** **in** the **cloud**
	- Apps usually run on a remote server
	- Local device only needs a keyboard, mouse, and screen
	- Sometimes called **Desktop as a Service (DaaS)**
- Has **minimal OS on** the **client device**
	- No huge memory, CPU needs, or a lot of storage
- **Needs network connectivity** due to a large network requirement
	- Everything happens across the network

### Application Containerisation
- **Container** = Has everything needed to run an application (code and dependencies)
- **Only runs app**, **not** an **entire** **OS**
- **Isolated process** in a **sandbox**
	- Self-contained
	- Apps can't interact with each other
- **Container Image** far smaller than a traditional VM
	- **Lightweight**, uses host kernel <- Can only run apps on same OS as host device unlike traditional VM
	- A standard for portability <- Move from one device to another without making changes to app container
	- Secure separation between applications
- **Communication between containers** **requires** **configuration** **via virtual networking**
- **Shared OS** between containers and host **can lead to** a **single point of failure**
- **If host OS compromised, all containers** are **exposed** due to their shared OS
- **Containerisation Software run on top of host OS e.g. Docker**