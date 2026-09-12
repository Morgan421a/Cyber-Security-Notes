### Virtualisation
- Allows **one physical device** to **run multiple operating systems** **at** the **same time**
- Virtual computer has a separate OS, independent CPU, memory, network, etc, allocated from the host's shared physical pool
	- For each virtual computer
- **Host-based virtualisation** <- Virtual computers hosted on a desktop
- **Enterprise environments** often use a **standalone server** that **hosts** the **virtual machines**
- Improves security of on-premise and cloud servers
- Reduces need for more physical machines
	- Reduces need for additional power, space, and cooling in server rooms as well as physical architecture in IT operations
- Each VM needs its own OS, updates, security patches, and hot fixes


### Sandboxing
- An **isolated testing environment used during** the **development process**
	- Used to **test different code** or **run apps, services and code in different operating systems** to see what differences or issues exist **without affecting** the **production environment**
	- Not connected to the real world or production environment
- Many VMs allow **snapshots** of configs to be taken, **allowing for roll backs** if needed
- Allows for multiple systems to be run and tested all at the same time

### Building an Application
- Develop in a secure environment
- Test in a separate virtual environment to ensure new features, bug fixes, etc. work correctly without affecting production code or causing issues

### Legacy Software and Operating Systems
- Some apps may only run on older operating systems (e.g. using Windows 11 but an app only works on Windows 10)
	- VMs allow apps to be run in the older OS on the same system without needing to build an entirely new machine
		- Run app instance in a separate VM

### Cross-platform virtualisation
- Running a different OS entirely on a system
	- i.e. running a Linux or macOS VM on a Windows System
	- Each OS has their own strengths and weaknesses
- VMs run on demand, can be opened and closed whenever a User desires
	- Seamless transitions between different operating systems without the need to reboot the computer
		- Saves time and resources <- No need to reboot to switch OS, all VMs running on same physical computer and sharing its resources
