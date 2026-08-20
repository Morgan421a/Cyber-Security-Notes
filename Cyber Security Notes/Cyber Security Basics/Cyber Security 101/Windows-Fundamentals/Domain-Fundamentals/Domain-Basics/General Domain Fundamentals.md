#### **Windows Domains**
- **Windows Domain** = A group of user and computers under the administration of a business
- Centralises the admin of common components of a Windows computer network in a single repo called **Active Directory (AD)**.
	- **Domain Controller (DC)** = The server that runs the **Active Directory** services
- Windows Domain's main **Advantages**:
	- **Centralised Identity management** - All users across the network can be configured from the [[glossary/Active Directory|AD]] with little effort
	- **Managing Security Policies** - Security policies can be configured directly from AD and applied to all users and computers across the network as needed

- Used in businesses, school/university networks, etc.
	- **Credentials** created and given to new individuals and are **stored** on the **AD**.
	- Upon attempting to login to any system on the domain, the machine **forwards** the **authentication process** back to the **AD** which then checks the credentials
	- This process allows a single set of credentials to be used across all devices on the domain rather than needing new credentials for each individual machine
- **Active directory** is also the **reason** behind **admin privileges** being **restricted** on domain machines:
	- Policies deployed throughout the network to prevent unauthorised access/control over domain computers

- **[[Group Policies]]** can be used to apply rules and restrictions to different **[[Active Directory Basics#^Organisational-Units|Organisational Units (OUs)]]** through the use of **Group Policy Objects (GPOs)**

- Domains can be individual or join together through **[[Trees, Forests, and Trusts]]**