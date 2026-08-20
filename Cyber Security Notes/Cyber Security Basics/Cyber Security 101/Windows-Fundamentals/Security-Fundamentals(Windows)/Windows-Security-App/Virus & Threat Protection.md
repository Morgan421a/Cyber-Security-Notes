##### **Virus & Threat Protection**
- Split into 2 parts:
	- **Current Threats**
	- **Virus & Threat Protection Settings**
- **Current Threats:**
	- Allows for the scanning of files on the device to check for potentially malicious files/programs, as well as the reviewing of previously flagged ones
	- **Scan Options:**
		- **Quick Scan** - Checks all folders on a system where threats are commonly found
		- **Full Scan** - Checks all files and running programs on the hard disk <- Takes much longer, potentially over an hour
		- **Custom Scan** - User can specify specific files and locations to scan
	- Files can be scanned directly by right clicking them and pressing the *"Scan With Microsoft Defender..."* Option

	- **Threat History:**
		- **Last Scan** - Date and results of the most recent scan <- can be results from both user initiated scans or automated **Windows Defender Antivirus** scans
		- **Quarantined Threats** - Threats that have been **isolated and prevented from running** on the device <- **Periodically removed** after **specified** amount of time (30 days by default)
		- **Allowed Threats** - Items that are flagged as threats but User has allowed them to run on the device <- **Only to be done if 100% certain it is a false flag or User knows what they're doing**

- **Virus & Threat Protection Settings**
	- Allows for the toggling, configuration, and updating of Virus and Threat Protection Settings for **Windows Defender Antivirus**
	- **Manage Settings:**
		- **Real-Time Protection** - Locates and stops malware from installing or running on the device; can be turned off temporarily before turning back on automatically
		- **Cloud-Delivered Protection** - Provides increased and faster protection with access to the latest protection data in the cloud
			- Device queries the cloud upon encountering a connection attempt to an unknown or suspicious IP address or domain.
				- If cloud service determines the destination is malicious, it sends a block signal back to the device, preventing connection before any data is exchanged
		- **Automatic Sample Submission** - Send sample files to Microsoft to help protect the user and others from potential threats
		- **Controlled Folder Access (CFA)** - Protects files, folders, and memory areas on the device from unauthorised changes by malicious or unknown apps.
			- Only approved and trusted apps are allowed to modify files in the protected folders
			- Specific folders are protected by default when CFA is enabled, and cannot be removed or disabled from the list
			- Requires **Real-Time Protection** to be turned on
		- **Exclusions** - Allows for files and folders to be excluded from the antivirus scanning. <- Done to reduce the number of false positives. 
			- **Excluded items could contain threats that make a device vulnerable. Should only be used by User's who 100% know what they're doing**
		- **Notifications** - WDA sends notifs with critical info about the device's health and security

- **Virus & Threat Protection Updates:**
	- **Check for Updates** - Manually check for updates to WDA definitions 
		- Definitions = Official termed **Security Intelligence**, refers to specific **digital fingerprints** and **behavioural rules** the antivirus uses to identify **known threats**

- **Ransomware Protection**
	- Requires **Controlled Folder Access** to be enabled