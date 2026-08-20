#### **User Accounts, Profiles, and Permissions**
- On typical local Windows systems, User Accounts can be one of two types:
	- **Administrator** - Can make changes to the system: add users, delete users, modify groups, modify settings on the system, etc.
	- **Standard User** - Can only make changes to folders/files attributed to the user; can't perform system-level changes i.e. installing programs

- Existing user accounts can be checked through a few ways
	- One way is:
		- Start Menu -> search "Other User" -> System Settings > Other Users Shortcut
			- Admins will see an "add or remove account" option
			- Clicking on local user account should bring up more options: Change account type and Remove

- When a user account is created, a profile is created for the user. 
	- Each user profile folder is under `C:\ Users` i.e. `C:\Users/John` <- for the user profile for the John user account
- Creation of a User's profile is done upon initial login
	- Shown through the "User Profile Service" message which shows while the user profile is being created
		- Post login, a dialog box will appear, indicating the profile is in creation

- `lusrmgr.msc` <- Used in run dialog box to access the Local User and Group Management menu
	- Shows list of all users and local groups on the system and allows for modification of them <- **Requires Admin Permission**
	- Each group has permissions set to it
		- Users are assigned/added to groups by the Administrator
			- Upon being assigned, the user inherits the permissions of that group
		- User can be assigned to multiple groups

#### **User Account Control (UAC)**
- Elevated Privilege to all users increases the risk of system compromise by increasing the chance and ease for malware to infect the system.
	- A user doesn't need to run with elevated privileges on the system in order to run tasks that don't require said privileges i.e. surfing the web, working on a word doc, etc.
		- **Principal of Least Privilege**
	- Since an elevated user account can make changes to the system, malware would run in the context of the logged-in user

- User account control (UAC) = Introduced by Microsoft to protect local users with aforementioned, elevated privileges (i.e. home PC users) 
	- By default, doesn't apply for the built-in local administrator account
	- First introduced with Windows Vista and continued in Windows versions that followed it

1. When user with an admin account logs in to a system, the session doesn't run with elevated permissions. 
2. When an operation needing higher-level privileges needs to execute, the user is prompted to confirm if they permit it to run (similar to Linux's `sudo` without the temp trust window)
	- UAC checks every time without caching