- **`regedit.exe` in `Run` dialog**
- The Windows Registry editor
	- **Stores information necessary to configure the system for users, apps, and hardware devices**
	- Contains info that's constantly referenced by Windows during operation
	- Essentially a master database
	- Has a **Hierarchical Structure**
- Used by almost everything:
	- Kernel, Device Drivers
	- Services
	- Security Account Manager (SAM)
	- User Interface, Applications
- **CRITICAL RESOURCE, DO NOT MAKE CHANGES UNLESS CERTAIN OF WHAT IS BEING DONE**
	- **BACKUP PARTICULAR PORTION OF THE REGISTRY PRIOR TO MAKING ANY CHANGES**
		- **Backup function built into regedit**:
			1. Click `File` -> Export 
			2. Select save location
			3. Choose from drop down whether to save as a **Registration File `*.reg`** (text export of selected branch) or a **Hive File `*.*`** (binary snapshot of a whole registry hive)
			4. Click `Save`
			- Run saved registry file to re-write backup into the registry
				- Merges backup with current registry:
					- Overwrites matching keys/values 
					- Creates keys in the file that don't exist
					- Keys created after the backup was taken are left untouched