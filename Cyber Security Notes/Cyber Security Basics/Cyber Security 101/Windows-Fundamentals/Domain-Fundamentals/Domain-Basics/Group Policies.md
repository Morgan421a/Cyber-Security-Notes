#### **Group Policies**
- **Group Policy Object (GPO)** -> A collection of settings that can be applied to OUs <- This is how Windows manages policies between OUs
	- Policies can be aimed at either users or computers, allowing a baseline to be set on specific machines and identities
- **Group Policy Management** Tool -> Used to configure GPOs <- Accessed via the start menu
	- To configure group policies:
		1. Create a GPO under **Group Policy Objects**
		2. Link the new GPO to the desired OUs where the policies should apply
- GPOs linked to an OU also link to any sub-OUs under it
- Policies can be linked to the domain itself to apply policies across the entire domain
- GPO details:
	- **Scope Tab** - Where the GPO is linked to the AD
		- **Security Filtering** - Allows for the application of the GPO to only the specified users/computers under an OU 
	- **Settings Tab** - Includes the contents of the GPO; tells user what specific configurations apply, separated into: *General*, *Computers*, and *Users*

- Each policy has an **Explain** tab to give more information regarding their purpose

##### **GPO Distribution**
- GPOs distributed to the network via a **share** called `SYSVOL` <- Stored in the DC
	- All users within a domain should usually have access to this share over the network in order to sync their GPOs periodically
	- `SYSVOL` share by default points to the `C:\Windows\SYSVOL\sysvol\` directory on each of the DCs in a network

- GPO changes may take up to **2 hours** to be reflected on the computers on a domain
	- Individual Computers can be forced to sync their GPOs immediately by running the command `gpupdate /force` on the desired computer
