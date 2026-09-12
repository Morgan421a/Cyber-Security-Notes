### Port Numbers
- Knowing Non-Ephemeral Port numbers is useful for: 
	- Troubleshooting apps and services
	- Configuring a firewall

### FTP - File Transfer Protocol
- **TCP/20** (active mode data) -> Used for transferring actual file content
  **TCP/21** (control) -> Used for establishing connections, authentication, and sending commands (e.g. file request or directory listings)
	- Transfers files between systems
- Typically requires authentication such as a username and password
	- Some systems use a generic/anonymous login -> allows anyone to login regardless of what the username or password are
- FTP is fully featured and on top of transferring files, some of its other features are:
	- List available files in a particular directory
	- Add/Delete files
	- Change file names
	- Perform administration functions

### SSH - Secure Shell
- **TCP/22** (Encrypted communication link)
- Similar to older **Telnet** protocol <- **Not typically used** **anymore** due to lack of encryption

### Telnet
- **TCP/23** (Telecommunication Network)
- Similar to SSH (e.g. uses a CLI, remote admin, etc.)
- **Lacks encryption** unlike SSH

### SMTP - Simple Mail Transfer Protocol
- **TCP/25** (Simple Mail Transfer Protocol)
	- Server to Server email transfer
- Also used to send mail from a device to a mail server
	- Commonly configured on mobile devices and email

### DNS - Domain Name System
- **UDP/53** (Converts domain names to IP addresses)
- Critical resource
	- Often multiple DNS servers in use for sake of redundancy

### DHCP - Dynamic Host Configuration Protocol
- **UDP/67** (assigned to DHCP Server) -> Listens for and receives incoming client requests (i.e. Discover and Request messages)
  **UDP/68** (assigned to DHCP Client) -> Listens for and receives server responses (i.e. Offers and Acknowledgements)
- DHCP used to automate the configuration of IP addresses, Subnet masks and other options
- **Requires** a **DHCP Server**
	- Server, Appliance, Integrated into a **Small Office/Home Office (SOHO) Router**, etc.
- Server has a **pool** of **available** IP addresses
	- When device connects to network it requests and IP address and config parameters from said pool (**Real time assignation from the pool**)
	- Each system is given a **lease** and must **renew** it at **set intervals** or give it back to the pool so it's available to use by another device
- Sys-admins can use DHCP to **manually configure** IP addresses to always be assigned to specific devices <- **DHCP Reservation**
	- Addresses assigned by MAC address in the DHCP Server
	- Allows addresses to be managed from one location

### HTTP and HTTPS
- **TCP/80** (HTTP) -> Web Server Communication **Not Encrypted**
- **TCP/443** (HTTPS) -> Web Server Communication **With Encryption**
- HTTP(S):
	- Used for communication in a browser and by other apps
- Majority of modern devices and servers use HTTPS (TCP/443)

### POP3 / IMAP
- Allow for the receiving of emails from an email server
	- Almost always requires user authentication prior to transfer
- **TCP/110** (POP3 - Post Office Protocol Version 3) -> Basic mail transfer functionality <- Downloads mail to the client and **typically** removes it from the server
- **TCP/143** (IMAP4 - Internet Message Access Protocol v4) -> Includes management of email inbox from multiple clients (devices) <- Keeps mail synced on the server so it can be accessed from multiple devices

### SMB - Server Message Block
- Protocol used by **Microsoft Windows**
	- AKA **CIFS - Common Internet File System**
	- File Sharing, Printer Sharing, or other processes where Windows needs to send data between different devices
- Using NetBIOS over TCP/IP (NetBT) <- Used by **Older Windows Devices** 
	- **UDP/137** (NetBIOS name services (nbname)) -> Similar to DNS, translates human-readable computer names into network addresses
	  **TCP/139** (NetBIOS session service (nbsession)) -> Sets up communication sessions between devices on a LAN
- **TCP/445** (NetBIOS-less communication/Direct communication) -> Direct SMB communication over TCP **without** the **NetBIOS transport** <- Commonly used for **Modern Windows Devices**

### LDAP / LDAPS
- **TCP/389** (LDAP - Lightweight Directory Access Protocol) -> Stores and retrieves data in a network directory; Commonly used in Microsoft **Active Directory**
- **TCP/636** (LDAPS -  Lightweight Directory Access Protocol Secure) -> Same as LDAP but uses encryption <- **Not necessary to remember 636 for A+ Exam**

### RDP - Remote Desktop Protocol
- **TCP/3389** (Remote Desktop Protocol) -> Used to share a desktop from a remote location; Commonly used to access and control Windows Devices on a network
- Can connect to an entire desktop or just one app
- RDP Clients exist to connect to other OS's, not just Windows, i.e. Linux, macOS, Android, iPhone, etc. 

### Ports to Memorise

|   Port   |                         Purpose                          |                                                                       Explanation                                                                        |
| :------: | :------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------: |
|  TCP/20  |                  FTP (Active Mode Data)                  |                                                                Transferring file content                                                                 |
|  TCP/21  |                      FTP (Control)                       |                                                Establishing connections, authentication, sending commands                                                |
|  TCP/22  |                    SSH (Secure Shell)                    |                                          Secure Remote connection to a device, controlled via a CLI (Encrypted)                                          |
|  TCP/23  |            Telnet (Telecommunication Network)            |                                           Remote connection to a device, controlled via a CLI (Not Encrypted)                                            |
|  TCP/25  |           SMTP (Simple Mail Transfer Protocol)           |                                        Server to Server email transfer, send mail from a device to a mail server                                         |
|  UDP/53  |                 DNS (Domain Name System)                 |                                                           Convert domain names to IP addresses                                                           |
|  UDP/67  | DHCP (Dynamic Host Configuration Protocol) (DHCP Server) |                           Listens for and receives incoming **client** requests such as **Discover** and **Request** Messages                            |
|  UDP/68  | DHCP (Dynamic Host Configuration Protocol) (DHCP Client) |                                Listens for and receives **server** responses such as **Offers** and **Acknowledgements**                                 |
|  TCP/80  |            HTTP (Hypertext Transfer Protocol)            |                                                         Web server communication (Not Encrypted)                                                         |
| TCP/443  |        HTTPS (Hypertext Transfer Protocol Secure)        |                                                           Web server communication (Encrypted)                                                           |
| TCP/110  |          POP3 (Post Office Protocol Version 3)           |                                         Receiving emails from an email server, basic mail transfer functionality                                         |
| TCP/143  |       IMAP4 (Internet Message Access Protocol v4)        |                                  Receiving emails from an email server, includes inbox management from multiple clients                                  |
| UDP/137  |    SMB (Server Message Block) using NetBIOS (nbname)     |                                          Convert computer names to network addresses (**Old Windows Devices**)                                           |
| TCP/139  |   SMB (Server Message Block) using NetBIOS (nbsession)   |                                    Sets up communication sessions between devices on a LAN (**Old Windows Devices**)                                     |
| TCP/445  |         SMB (Server Message Block) NetBIOS-less          |                               Direct SMB communication over TCP without the NetBIOS transport (**Modern Windows Devices**)                               |
| TCP/389  |       LDAP (Lightweight Directory Access Protocol)       |                              Store and receive data in a network directory; commonly used in Microsoft **Active Directory**                              |
| TCP/3389 |              RDP (Remote Desktop Protocol)               | Share a desktop from a remote location; Commonly used to access and control Windows devices on a network, Other OS's have their own clients to do so too |
