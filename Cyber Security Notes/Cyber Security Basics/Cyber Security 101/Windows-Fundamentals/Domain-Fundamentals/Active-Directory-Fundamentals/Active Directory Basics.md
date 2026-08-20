#### **Active Directory**
- **Active Directory Domain Service (AD DS)**  = **Service** that stores information of all the "objects" that exist on the network. Some objects supported by AD include:
	- **Users** - Leaf Object
	- **Machines** - Leaf Object
	- **Groups** - Container Object
	- Shares - Leaf Object (Can store objects, but not AD objects, hence Leaf object)
	- Printers - Leaf Object
- There are two types of **Objects** in an AD network:
	- **Container** - AD objects that **Can contain** other **AD objects** within them; e.g. **Organisational Units (OUs)** and **groups** are classed as container objects
	- **Leaf** - AD objects that **Cannot contain** other **objects** within them; e.g. **Computers**, **Users**, and **printers**

- ##### **Users:**
	- One of the most common objects in AD
	- Apart of the **Security Principals** category:
		- Objects apart of this category can be authenticated by the domain and assigned privileges over **resources** like files or printers
			- **Security Principal** = An object that can act upon resources in the network
	- Users can be used to represent two types of entities:
		- **People** - persons in the organisation that need to access the network, i.e. employees or students
		- **Services** - Every service requires a user to run -> different from regular users, only have privileges needed to run their specific service. e.g. IIS or MSSQL services

- ##### **Machines:**
	- For every computer that joins the AD domain, a machine object is created.
	- Considered **Security Principals** 
	- Assigned an **account** just like a regular user
		- **Account rights** somewhat **limited** within the domain itself
		- Machine account passwords = **automatically rotated** out, generally made up of **120 random characters**
		- Machine account **naming scheme** = **Computer's name** followed by a **dollar sign (`$`)** e.g. computer `DC01`'s machine account = `DC01$`

- ##### **Security Groups:**
	- Considered **Security Principals**
	- Groups can have both users and machines as members
	- Groups can include other groups
	- **Some groups** are **created by default** in a domain that can be used to grant specific privileges to users, some **security groups** are **auto assigned** upon **account creation**
		- Some of the most important groups in a domain are:
			- **Domain Admins** - Users have admin privileges over entire domain, by default can administer any computer on the domain, including the **Domain Controllers**
			- **Server Operators** - Users can administer **Domain Controllers**; can't change admin group memberships 
			- **Backup Operators** - Users can access any file, ignoring their permissions; used to perform backups of data on computers
			- **Account Operators** - Users can create or modify other accounts in the domain
			- **Domain Users** - All existing user accounts in the domain
			- **Domain Computers** - All existing computers in the domain
			- **Domain Controllers** - All existing Domain Controllers on the domain
	- Real world example: 
		- **OUs** can be used to **split up departments**, **Security Groups** can be used to **split up permissions** by the ranks within those departments. 
			- e.g. Interns in the IT department have the lowest privileges, IT managers in the department have the highest privileges
			- Good for scalability <- Just move promoted individuals to a different security group

##### **Active Directory Users and Computers**
- Users, Groups, or Machines in the Active Directory can be configured by logging in to the **Domain Controller** and running "*Active Directory Users and Computers*" from the **Start Menu**
- Shows hierarchy of Users, Groups, and Computers that exist in the domain
- Objects organised in **Organisational Units (OUs)**
	- **Organisational Units (OUs)** = Container objects that allow for the classification of users and machines ^Organisational-Units
	- Mainly used to define sets of users with similar policing requirements.
- A **User** can only be part of **one OU at a time**
- Simple tasks can be performed on users within an OU such as creating, deleting or modifying them as needed
	- **Can also be used to reset passwords if needed**
- Windows creates some default OUs including:
	- **Builtin** - Contains default groups available to any Windows host
	- **Computers** - Default location for any machine joining the network; they can be moved if needed
	- **Domain Controllers** - OU that contains the DCs in the network
	- **Users** - Default users and groups that apply to a domain-wide context
	- **Managed Service Accounts** - Stores accounts used by services in the Windows domain

##### **Security Groups vs Organisational Units**
- **OUs** -> Used for **applying polices** to users and computers, which include specific configs pertaining to sets of users depending on their role in the enterprise. <- A User can only be in one OU at a time
- **Security Groups** -> Used to **grant permissions over resources** i.e. allowing some users to access a shared folder or network printer. <- A User can be part of many groups, which is needed to grant access to multiple resources 