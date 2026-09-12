### Multifunction Devices (MFD)
- **Multifunction Devices (MFDs) combine printing, copying, scanning and, sometimes, faxing functionalities**
- **Connect to a network** (Can be **wireless** **or wired**)
- May have a phone line connection (fax capabilities)
- May be able to print from the web
- More functions = greater risk of things going wrong
- Example Devices:
	- Printer
	- Scanner
	- Fax

### Installing MFDs
- Can be **large devices**
	- Check available space prior to purchase/installation
	- May need to be set up in an area outside of normal walkways
- **Move device to installation location before unboxing**
- Area of installation should:
	- Have **access to a power connection without** using **extension cords**
	- Have a **network connection**
	- Be **Accessible to all who need to use** the **device** **while not blocking doorways** **or high-traffic environments**
	- Be a **stable surface** that can **support** the **device's weight**
		- **Some MFDs** (e.g **heavy printers**) need **dedicated printer stands**
	- Be **well-ventilated to disperse toner or ink fumes**
	- Be **away from public or easily accessible areas for security**
	- Be **kept clear of clutter to prevent accidents**
- Using **long cables should be avoided** as they **can become trip hazards**
- **Allow device to adjust to room temp** **if** it was **stored** **in** a **hot or cold environment**
	- Roughly **1-2 hours** to **prevent condensation** **inside** the **printer**
#### Setup process
1. Place printer in chosen location
2. Connect power using appropriate power cable
3. Install consumables, such as ink or toner cartridges, paper trays and feeders
4. Turn printer on and allow it to finish initialisation
5. Install drivers and software on computers intent on using the device
6. Configure network settings, if applicable
	- Static or dynamic IP config
	- Wi-Fi settings or direct Ethernet connection
7. Carry out test print to check functionality
#### Common setup issues
- **Printer not recognised by computer** -> Ensure proper drivers installed, check cable connections and ports
- **Print quality issues** -> Do print head alignment and cleaning process, make sure correct paper type and settings are used
- **Paper Jams** -> Follow on-screen prompts to remove jammed paper safely, avoid overloading paper trays

### Printer Drivers
- **Printer Drivers** = Software installed on a computer to **translate print commands into** a **format** the **printer can understand**
	- Provides flexibility by supporting multiple printers with a single software interface
- **Facilitate communication between** an **OS** **and** the **printer**
- **Converts app data into printer specific commands**
- Allows OS to manage print jobs efficiently
- Enables use of advanced printer features
- **Specific to each printer model**
- Driver needs to be correct for each computer's operating system (Window 10, 11, etc.)
	- Correct version for OS must be installed as well (32-bit or 64-bit driver)
- Needs to be installed on all computers intent on using the printer

### Page Description Languages (PDLs)
- **PDLs** = Languages used by printers to convert digital content into print-ready format
- **PCL** (Printer Command Language)
	- Developed by **HP**
		- Proprietary and **optimised for HP printers**
	- Offers **faster processing for standard business printing needs**
	- Supports **scalable fonts**, **vector graphics**, and **colour printing**
	- **Commonly used across the industry**
- **PostScript**
	- Developed by **Adobe**
	- Device-independent, widely used in professional publishing
	- Ensures accurate screen-to-paper output
	- **Popular with high end printers**
		- Often used for graphic design and professional printing environments
- Drivers need to match the printer
	- PCL printer = PCL driver
	- PostScript printer = PostScript driver

### Firmware
- **Embedded software within a printer that manages its hardware operations**
	- **Controls a printer's print speed, quality, connectivity, and internal processes**
	- The **internal "Operating System" of a multifunction device**
		- Starts the system
		- Connects to the network
		- Interprets incoming data stream
		- Runs the printing process
- Firmware **needs to be updated**
	- Improves performance and print quality
	- Fixes bugs and security vulnerabilities
	- Adds new features and enhances compatibility with modern OS's
	- Latest Firmware typically available on MFD's website <- Should be **install**ed **from** a **stable platform and power source**
		- Follow update instructions from manufacturer
		- Printer **MUST** **remain powered during updates** to **prevent corruption or damage**

### Wired Device Sharing
- Multiple interfaces used to connect to MFDs
	-  May include more than one option
		- e.g. connecting a printer to a computer and a network using both USB type B and Ethernet
- Some wired interfaces include:
##### **USB**:
- Common connector
- USB **type B on** the **printer**, USB **type A** or **USB-C** **on** the **computer**
	- **Or USB-C everywhere**
 - Direct **one-to-one connection** between printer and a computer
 - **Some OS's** such as **Windows** and **macOS** have **plug-and-play support** <- Automatically detect and install drivers once connected
 - **Advantages**:
	- Easy setup
	- No network config needed
	- Reliable and fast data transfer
 - **Disadvantages**:
	- Limited to one computer at a time
	- Cable length restrictions can limit placement
#####  **Ethernet**:
- **RJ45 Connector** plugs **into** **printer**
- Used to **connect directly to** a **network**
- **Printer connected to** a **switch** **or** **router** via Ethernet cable
- **IP address config**:
	- DHCP <- Automatic IP address assigning
	- Manual Config <- Static assignment, makes for easier network management	
- **Install printer drivers on each computer needing access**
- **Web-based interface** <- Access printer settings through assigned IP address in a web browser
- **Advantages**:
	- Multiple users can access printer over a network
	- Faster and more stable than wireless connections
	- Allows for remote management through web interfaces
- **Disadvantages**:
	- Network cables need to be run to printer location
	- Network security measures may need to be considered

### Wireless Device Sharing
- Another way to connect MFD devices, some ways include:
#### **Bluetooth**:
- **Short range**, **wireless connection** <- replaces need for USB cables
- **Direct communication between** a **device and printer**
- **Advantages**:
	- Quick and easy setup for personal devices
	- No need for Wi-Fi or Ethernet
- **Disadvantages**:
	- Limited Range (Often around 30 feet)
	- Not suitable for shared environments or high-volume printing
#### 802.11 (Wi-Fi) Connectivity
- **Advantages**:
	- More flexible printer placement due to no cables for connection
	- Allows multiple devices to connect
	- Offers remote printing capabilities <- If supported
- **Disadvantages**:
	- Wireless networks prone to interference
	- Performance may vary depending on signal strength and network congestion
##### 802.11 Infrastructure Mode:
- **Printer connects to** an **existing Wi-Fi network** (router/access point)
- Functions similarly to an Ethernet Connection
- **IP address** can be **assigned** **manually** **or** through **DHCP**
-  Allows every other device on the network to communicate with the MFD
- Good for shared office environments
##### Wi-Fi Direct Mode:
- **Printer acts as** its own **access point** and **broadcasts** **an SSID** (Service Set Identifier (Wi-Fi network name))
- **Devices** can **connect directly without** the **need for** a **router**
- Good for quick, temporary connections
##### 802.11 Ad hoc mode:
- No Access Point used
- Direct link between wireless devices
- Largely obsolete peer-to-peer technology


### Sharing The Printer
- **Printer Share**
	- Printer is connected to a computer
	- Computer shares the printer
		- Typically **through** the `sharing` **tab** **in** the **printer properties on Windows**
	- **Host computer needs to be running**
	- **Advantages**:
		- Simple and cost-effective for a small number of users
		- No need for additional hardware or server management
	- **Disadvantages**:
		- Host computer must be powered on for printer availability
		- Performance may degrade with multiple users
- **Print Server**
	- A **separate service**, **typically running inside** of the **printer** itself, though **can be an external print server**
	- Allows print jobs to be sent directly to the print server
	- Print server manages printing process to MFD
	- **Jobs** are **queued and managed on** the **printer**
	- **Usually** have a **Web-based front-end or Client utility for management**
		- Shows print jobs in queue, allows jobs to be added or removed
	- Can be managed through tools such as: 
		- **Windows Print Management MMC** (Microsoft Management Console)
			- Centralises printer sharing
			- Monitors print queues
			- Facilitates troubleshooting
	- **Advantages**:
		- Centralised management of multiple printers
		- Remote config and troubleshooting capabilities
		- Queue management to optimise printer usage
		- Cost reduction by optimising printer availability and maintenance

### Configuration Settings
- **Duplex**
	- **Print on both sides of page** without manually flipping paper over
	- Saves Paper
	- **Not all printers** have the capability
- **Orientation**
	- **Portrait vs. Landscape**
	- Paper doesn't rotate
	- Printer compensates by printing in chosen orientation
- **Tray Settings**
	- **Printers can have multiple paper trays**
	- May have different types of paper in each tray, e.g. plain paper, letterhead, etc.
	- **Choose** correct **tray in print dialogue**
- **Quality**
	- Resolution during output (Sometimes called "print quality")
	- Colour or Greyscale
	- Colour saving mode <- If printing in colour; uses less ink but may result in lighter text and smudged prints

### Printer Security
- **User authentication**
	- Can be used to **limit who's allowed to print on an MFD** by **requiring** a **Username**, **password**, or **other authentication mechanisms**
	- Set rights and permissions
	- **Who can print** and **who can manage** the device
		- **Principle of least privilege** <- Users should only have the permissions needed to complete their tasks
	- Typically **set through the `security` tab** **in** the **device's properties on Windows**
	- **Benefits**:
		- Prevents unauthorised access to sensitive data
		- Reduces accidental printing to incorrect printer
		- Enhances data security by restricting access based on role
- **Badging**/**RFID Badges**
	- **RFID badges used as an authentication method to release print jobs securely**
	- Print job sent to a printer but not printed until a badge is used to authenticate a user
	- Quick and easy access to secured print jobs
	- **Benefits**:
		- Simplified authentication process for users
		- Reduces time spent entering credentials manually
		- Enhances tracking and accountability for printed documents
- **Audit Logs**
	- **Record All print jobs processed by a printer**
	- Tracks details such as who printed, when they printed, and what was printed
	- Often **included in the printer or print server** itself **or** **in** the **OS used to share** the **printer**
		- Can also be found in the **Windows Event Viewer / System Events utility**
	- **Provides accountability** by tracking user activity
	- **Helps investigate printing anomalies** (e.g. excessive printing or unauthorised document printing)
	- **Can be integrated with SIEM** (Security Information and Event Management) **systems for centralised monitoring**
	- **Benefits**:
		- Helps in training employees on proper printing practices
		- Good for **cost management** and **security monitoring**
		- Supports compliance requirements for sensitive data handling
	- **Implemented by**: 
		- enabling audit logging in the printer's management interface
		- Configuring network printers to send logs to a centralised logging system
- **Secured Prints**
	- Allows **passcode** (e.g. a PIN) to be **defined** **for** a **printer**
	- **Passcode must be entered at printer before printing starts**
		- Prevents sensitive documents from being left unattended at the printer
	- **Advantages**:
		- Reduces wasted prints due to accidental submissions
		- Prevents unauthorised access to printed documents
		- Ensures document confidentiality by allowing users to retrieve print jobs securely
	- **Disadvantages**:
		- Can increase waiting times for large print jobs
		- Users must be physically present to start the printing process
	- **Printer must support secure printing**

### Flatbed Scanner/Scanning Services
- Can be used to **turn physical documents into** a **digital format**
- Common in modern MFDs
	- All-in-one MFD
- **Can be** a **standalone Flatbed**
- **May include an ADF** (Automatic Document Feeder)
	- Allows multiple pages to be scanned at a time instead of putting one down, scanning it, taking it off, and putting down the next
- **OCR** (Optical Character Recognition) = Technology that **converts scanned images into editable digital text**
	- Allows for the modification of scanned text in word processors
	- Facilitates document archiving and searchability
	- Useful for converting legacy hard copy documents to digital formats

### Network Scan Services
- **Modern MFDs** can **scan documents** and **email results** of a scan **to** an **inbox** using SMTP (Simple Mail Transfer Protocol)
	- Allows for immediate distribution of scanned documents
	- **Fine for small scans** but **large scans can fill up a mailbox**
- **Scan directly to** a **share drive on** a **network** **using SMB** (Server Message Block)
	- Sometimes called "**Scan to Folder/Network Folder**"
	- Effectively sending scans to an existing Microsoft Share where they can be accessed in a digital form
	- Enables centralised access to scanned files across an org
- **Scan to Cloud**
	- **Scanned files uploaded to cloud services** such as **Microsoft One Drive**, **Google Drive Dropbox**, **Apple iCloud**, etc.
	- Provides remote access to scanned documents from any device

