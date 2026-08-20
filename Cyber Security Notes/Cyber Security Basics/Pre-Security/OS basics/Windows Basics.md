**Car Park**

**Logging in and Authentication**
- Three commonly used account types with different system permissions:
	- **Guest** - **Restricted account** intended for **temp access**, minimal permissions, no ability to change sys settings
	- **User** - User account for everyday tasks, i.e running apps and changing personal settings, **no access to sys-wide changes**
	- **Administrator** - **Highest level of permissions**, full control over the system, including, software installation, config changes, user management

**Securing Windows**
- **Keep OS up to date** <- Ensures latest security patches, performance updates and bugs fixes are installed
- **Native windows Security** - Built-in tools to protect Windows systems from threats i.e. malware, insecure apps, unauthorised network access, etc.
	- Windows Security App - Central dashboard to manage Windows' built-in protection measures, has four main sections each with a different focus:
		- **Virus & Threat Protection** - Detect and remove malicious software through real-time protection and customisable scans
		- **Firewall & Network Protection** - Controls network traffic (both ways) to help prevent unauthorised access
		- **App & Browser Control** - Protects uses from potentially unsafe apps, files and websites
		- **Device Security** - Provides hardware-based protections that help secure the sys

- **Virus Scan Results & Actions** - Files seen as potentially malicious will have 3 actions available:
	- **Allow** - Adds file to **Allowed Threats** list, **Permanently exempts** it from future scans and alerts. <- Should only be used for trusted software that's incorrectly flagged as a false positive
	- **Quarantine** - Moves file to a **secure, isolated location** where it can't run or harm the sys. File stays there and can be restored later if determined to be a false positive
	- **Remove** - **Permanently deletes** the file from the device, **irreversible**, file cannot be recovered or restored from anywhere

- **Windows Defender Firewall** - Built-in firewall designed to protect computer from unauthorised network traffic.
	- Monitors traffic and applies rules, configured by admin, to determine if connections are allowed or denied.
	- Operates on different network profiles, allowing for the creation of custom rules or specify permitted apps.
		- **Domain** - Used when a sys is connected to an org's domain network
		- **Private** - Intended for trusted networks i.e. home or lab enviro
		- **Public** - Used for untrusted networks i.e. public WiFi


**Configuring Windows**
- **Control Panel** - Legacy management interface, provides access to older sys config tools that are still required for specific admin tasks
- **Task Manager** - Real time system monitoring, five tabs which track:
	- **Processes** - Currently running apps and background processes, and their resource usage
	- **Performance** - Graphs and stats for sys resources such as CPU, memory, network, etc.
	- **Users** - Currently logged-in users and used resources
	- **Details** - More detailed view of running processes, including process IDs (PIDs)
	- **Services** - Windows services and their current status (running or stopped)

**Key Terminology**
- **DOS** - Computer OS that provides a file for sys ops i.e. reading, writing and erasing data on a disk
	- Non-graphical line-oriented command-driven OS designed for the IBM PC
	- Several variants, such as MS-DOS (Microsoft) and PC-DOS (IBM)
	- In simple terms -> Command line environment that allowed for data control/management


## **Summary**
- **Three most common Windows accounts:**
	- **Guest** - Lowest level of permissions, restricted to only do what is configured by the administrator app and data wise. Cannot configure personal or system settings
	- **User** - Able to use apps and access the file system freely, however is still restricted from accessing/modifying select files. Can change personal configuration but not make any system wide changes (app or system config-wise)
	- **Administrator** - Highest level of permissions, can access/modify any system files and make system-wide changes

- **DOS** - OS that allowed for the creation, modification and interaction of data on a computer.
	- Used a command line environment for interaction through the use of commands
	- Precursor to modern GUI based OS's
	- 2 Popular examples were
		- PC-DOS (IBM computers)
		- MS-DOS (Microsoft's computers)

- **Configuration**:
	- Can be done through the standard settings menu
	- More advanced configuration can be done through the control panel 
	- **Task manager** - Live System monitoring software, has 5 tabs:
		- **Processes** - Shows all processes currently running and their resource usage
		- **Performance** - Shows live graphs and data of hardware components such as CPU, memory, GPU etc
		- **Users** - Shows users currently logged in on the system and their resource usage
		- **Details** - Shows a more detailed information of each process currently running
		- **Services** - Shows Windows processes exclusively and their resource usage

- **Security:**
	- **Keep Operating System up to date** to ensure newest security patches, bug fixes and performance updates are installed
	- **Windows Security App** has 4 main sections, each with their own purpose and settings:
		- **Virus and threat protection** - Allows for customisable and automatic scans of system files to detect potentially malicious files or software.
			- Flagged file options are:
				- **Allow** - Become exempt from all future scans and run as normal
				- **Quarantine** - Isolated from system, good for further investigation. Files can be recovered later and used as normal after
				- **Remove** - Data deleted entirely and removed from system, data is unrecoverable and process is irreversible
		- **Firewall and Network Protection** - Allows for control of incoming and outgoing network traffic through customisable rules/configuration as well as Window's own profiles
			- Window's profiles are:
				- **Domain** - Used for workplaces, all traffic from devices connected on same domain is permitted
				- **Private** - Used for private network connections, only traffic from devices on the same network is allowed
				- **Public** - Used when connected to a public network, restricts traffic from unauthorised devices unless specified otherwise
		- **App and Browser Control** - Protects users from potentially unsafe apps, files and websites
		- **Device Security** - Provides hardware based protections that help secure the system