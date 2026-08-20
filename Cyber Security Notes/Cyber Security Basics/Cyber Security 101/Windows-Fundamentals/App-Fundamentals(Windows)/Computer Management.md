- `compmgmt.msc` in run
- Has 3 Primary Sections:
	- **System Tools**:
		- **Task scheduler** - Used to create and manage common tasks for computer to do automatically at specified times 
			- Task Scheduler Library <- shows all scheduled tasks of system, clicking one shows its details, including the command that will run when the task is triggered
			- Tasks can be configured to run one-time or recurring
		- **Event Viewer** - Displays events that have occurred on the computer system. 
			- Used to diagnose problems and investigate actions executed on the system
			- Five types of events that can be logged, briefly they are:
				- **Error** - Event that shows a Significant problem such as data loss or functionality i.e. CPU failure leading to system crash
				- **Warning** - An event which isn't necessarily significant, but may indicate a possible future problem i.e. low disk space
				- **Information** - Event which describes successful operation of an app, driver or service i.e. network driver loads successfully. 
					- Generally inappropriate for desktop app to log an event each time it starts
				- **Success Audit** - Event that records an audited security access attempt that is successful i.e. user's successful login attempt
				- **Failure Audit** - Event that records an audited security access attempt that fails i.e. user tried to access a network drive and fails

			- Standard logs are displayed under **Windows Logs**, each log in short is:
				- **Application** - Events logged by apps i.e. database app might record a file error 
					- App dev decides which events to record
				- **Security** - Events such as logon attempts, or those related to resource use. 
					- Admins can start auditing to record events in the security log -> not all categories monitored by default and need to be added before they can be audited
				- **System** - Events logged by system components i.e. drive failure or other system component to load during startup
				- **Custom Log** - Event logged by apps that create a custom log.
					- Allows apps to control size of the log or attach ACLs for security purposes without affecting other apps
						- ACL = Access control list -> Security config which explicitly defines which users or groups can read, write, or clear the specific log

		- **Shared Folders** - Shows a list of shares and folders shared that others can connect to via SMB (Standard Port = 445)
			- Shares - List of shares on the computer, such as the default share of Windows can be seen `C$`, as well as the default remote admin shares created by Windows such as `ADMIN$`
				- Properties of each folder can be viewed including permissions
			- Sessions - List of users that are currently connected to the shares
			- Open Files - Lists folders and/or files which the connected users access

		- **Local Users and Groups** - Shows list of users on the system and information about each

		- **Performance** - Where the **performance monitor (`perfmon`)** utility can be seen and accessed
			- Shows performance data in either real-time or from a log file. <- useful for troubleshooting performance issues on a system, whether local or remote

		- **Device Manager** - Allows hardware to be viewed and configured i.e. disabling hardware attached to the computer

		- **Storage** - Has both Windows Server backup and Disk Management
			- Disk Management - System utility allowing for advanced storage tasks such as:
				- Setting up a new drive
				- Extending a partition
				- Shrinking a partition
				- Assigning or changing a drive letter (e.g. E:)
			- ==Windows Server Backup - Come back to later ==

		- **Services and Applications** - Lists all services and their statuses <- under Services section
			- Service Startup type = how and when the service is configured to start, primary types are:
				- Automatic - Start every time system boots
				- Automatic (Delayed Start) - Starts shortly after system has finished booting
				- Manual - Only starts when another process or user triggers the service
				- Disabled - Shouldn't run at all
			- WMI Control - configures and controls the **Window Management Instrumentation (WMI)** 
				- WMI allows scripting languages such as VBScript or Windows PowerShell to manage Windows PCs and Servers, both locally and remotely
				- Microsoft provides a CLI to WMI called Windows Management Command-Line (WMIC)
					- WMIC deprecated in Windows 10, version 21H1. superseded by PowerShell for WMI 
