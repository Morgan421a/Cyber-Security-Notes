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
- 

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