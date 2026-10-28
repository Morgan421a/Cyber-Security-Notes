- **`net` <- Family of Windows Network Commands** 
	- Without parameters, shows all available syntax

- **`net view` <- View network Resources**
	- `net view \\<servername>`
	- `net view /workgroup:<workgroupname>`

- **`net use` <- Map a network share to a drive letter**
	- `net use drive: \\<servername>\<sharename>`

- **`net user` <- Displays info about user accounts on a local computer or domain, can be used to add, modify, or delete user accounts**
	- `net user <username>` <- Show information about a specific user account
	- `net user <username> * /domain` <- Used to reset a domain user's password -> Admin privileges required