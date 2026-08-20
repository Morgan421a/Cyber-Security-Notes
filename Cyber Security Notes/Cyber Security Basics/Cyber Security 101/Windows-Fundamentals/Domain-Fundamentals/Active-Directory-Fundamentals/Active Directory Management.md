#### **Managing Users in AD**
- OUs **protected** against **accidental deletion** by default
	- **Advanced features** must be enabled under the *View* tab
		- Shows some additional OUs and enables user to **disable accidental deletion protection** by right clicking an OU and going to *Properties* -> adp checkbox found under the *Object* tab
	- Any Users, Groups or OUs within a deleted OU will **also be deleted**

- AD allows control over some OUs to be given to specific users <- Process called **Delegation**
	- **Delegation** = Allows specific privileges to be granted to users to perform advanced tasks on OUs without needing a Domain Admin to get involved
		- Commonly used to grant `IT Support` privileges to reset other low-privilege users' passwords
- OU control can be delegated by: 
	1. Right clicking the specific OU which will open the **Delegation of Control Wizard** 
	2. Click add then type the name of the user to whom control will be delegated
	3. Use the check names button to allow Windows to autocomplete the user <- Helps avoid mistyping of users' name
	4. Selecting the tasks to delegate to the User or even creating custom ones
	5. Click next, review the changes, and if correct, click finish

#### **Managing Computers in AD**
- **By default**, all machines that join a domain (aside from DCs) are put in the "Computers" OU
- Good idea to segregate devices according to their use; generally, devices would be divided into at least 3 categories:
	- **Workstations:** 
		- One of the most common devices within an AD domain 
		- Each user in the domain will likely be logging into a workstation. <- The device they'll be using to do their work or normal browsing activities
		- These devices **should never have a privileged user signed into them**
	- **Servers:**
		- Second most common device within an AD domain
		- Generally used to provide services to users or other servers
	- **Domain Controllers:**
		- Third most common device within an AD domain
		- Allow for the management of the AD Domain
		- These devices are often deemed the **most sensitive devices** within the networks as they **contain hashed passwords** for all **user accounts** within the environment