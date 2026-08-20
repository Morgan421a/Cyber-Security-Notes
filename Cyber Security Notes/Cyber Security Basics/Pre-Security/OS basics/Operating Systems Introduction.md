**Car Park**
- Tiny footprint for embedded devices? = Low system resources needed to run them
- Unix vs Linux?
	- **Linux** - Unix-like OS, **Open-source**, generally **free to use and modify**, highly **portable**, often used for web servers, cloud infrastructure and embedded systems
	- **Unix** - Typically **Closed-Source**, requiring **paid licenses** from vendors i.e. IBM, Oracle, HP, usually designed for specific **high-end hardware**, used more for legacy enterprise enviros

**What An Operating System Is**
- **Operating System (OS)** - **Software** that sits between the applications and hardware of a device in order to co-ordinate between them ensuring the device runs as one unified system
	- User -> Apps -> OS -> Hardware
	- OS handles the organising of **resources** (CPU, memory, storage and all hardware components)
		- Removes the need and risk of giving applications direct control over these resources, which would cause conflicts

- **Kernel Space** - The core of the OS where the kernel operates and manages hardware and system resources directly -> Has unrestricted access to CPU, memory, storage and all hardware components
- **User Space** - Where apps run, deliberately restricted from accessing hardware directly. -> Must make a system call and request the kernel to act on their behalf when trying to carry out a function i.e. open or save a file, connect to WiFi etc.
	- Separation of both increases the **reliability** of OS by **preventing** faulty apps/conflicts between apps from **crashing** an entire system

- **Duties of the Operating System:**
	- **File System Management**
		- Organise files into dir(s), handles naming, paths, permissions, metadata (name, size, type, timestamps)
	- **Memory Management**
		- Allocate RAM to processes, keep app memory isolated from other processes, reclaim memory when apps close, OS uses virtual memory when RAM runs low to keep system stable
	- **Process Management**
		- Create, Schedule, Prioritise, and terminate running programs. OS decides how much CPU time each process gets <- improves multi tasking QoL
	- **User Management**
		- Handle multiple user accounts, authentication and permissions to determine who can access what
	- **Device management**
		- Load drivers and provide a UI (hardware abstraction layer), allows apps to make requests to these devices i.e. mouse, printer, external HDD <- also allows them to work instantly on plug in

- OS also **enforces its own security measures** before any firewall, antivirus or other security tool does, some of these are in a basic sense:
	- **Authentication** - Verifies users through login passwords and biometrics
	- **Permissions** - Handles exactly what each user and app is allowed to view, change or interact with (read, write or execute)
	- **Isolation** - Keeps every process isolated from each other (Kernel/User space separation)
	- **System Protection** - Safeguards critical system files and setting from unauthorised changes

**OS Interaction and Landscape**
- **OS Interface** allows users to interact with OS, the two main forms of interface are: 
	- **Graphical User Interface (GUI)** - Visualised data and Icons for user interaction <- Simplifies interaction for users, improving QoL
	- **Command Line Interface (CLI)** - Text-based interaction via a terminal/console, more precise control than GUI but requires knowledge of both the syntax and commands that the OS understands

- Different types of OS's exist to suit different purposes, 5 most common ones are:
	- **Desktop**
		- Primary uses = PCs, daily work, gaming content creation
		- Detailed GUI, runs many apps at once, user-focused
	- **Server**
		- Primary uses = Web hosting, databases, cloud services, back-end
		- No GUI (Headless), max uptime, multi-user, remote access
	- **Mobile**
		- Primary uses = Smartphones and Tablets
		- Touch-based UI, power efficient, always connected, app sandboxing
	- **Embedded**
		- Primary uses = Appliances, IoT devices, smart TVs, routers
		- Tiny footprint (Low resource requirement), runs on limited hardware
	- **Virtual/Cloud**
		- Primary uses = Lab machines, containers, cloud instances
		- Lightweight, scalable, rapid deployment

- Example OS's for 5 most common types:
	- **Desktop**
		- Windows - Most popular OS for PCs *Windows 10 (End of Life), Windows 11*
		- macOS - Apple's desktop OS, clean GUI and integrates with other Apple devices *Sonoma (14), Sequoia (15), Tahoe (26)*
		- Linux - Family of open-source OS's called distributions *Ubuntu, Debian, Fedora*
	- **Server**
		- Windows - Used for large networks, data centres and corporate enviros *Server 2016, 2019, 2022, 2025*
		- Linux - Majority of web servers, reliable and open-source *Ubuntu Server, Debian, CentOS, Red Hat*
		- Unix - Large enterprises, finance, telecom, government *IBM AIX, Oracle Solaris*
	- **Mobile**
		- Android - Most widely used OS for mobile, runs on phones, tablets and smart devices *Android 14 - 17, Manufacturer Versions*
		- iOS - Apple's Mobile OS running on iPhone, iPad and other devices *iOS 17, 18, 26, 26.5*
	- **Embedded and IoT Devices**
		- Embedded Linux - Specialised OS built into devices with dedicated functions *OpenWrt, Ubuntu Core, Yocto Project*
		- Real-Time OS - Designed for apps where tasks need guaranteed response times (aircraft controls) *FreeRTOS, VxWorks, QNX*
	- **Virtual and Cloud**
		- Cloud/VM - Massive data centres that host websites, apps and streaming services *Ubuntu LTS, Amazon Linux, Rocky Linux*
		- Container-Optimised - Lightweight alternatives to VMs that package only the app and its dependencies *Alpine Linux, Bottlerocket AWS, Flatcar Linux*

- Many OS's exist to suit the different devices and environments they operate within, each providing different capabilities i.e. stability, security, consistency, optimisation, user QoL etc.
	- OS Devs will also design different OS's with specific goals such as ease of use, performance, security, openness, customisation etc


### **Key Terminology**
- **Operating System** (OS) - Core software that manages hardware, apps and all system resources
- **Kernel Space** - Where kernel exists, which directly manages hardware and system resources
- **User Space** - Where apps run with limited permissions for safety and system stability
- **Graphical User Interface** (GUI) - Visual interface of an OS, windows, icons, menus that allows for interaction through clicking and tapping
- **Command-Line Interface** (CLI) - Text-Based interface to enter commands to control the system with more precision and speed than the GUI


## **Summary**
- Operating System (OS) - Software that sits between the hardware, applications and user (HW -> OS -> app -> User) of a device
	- Allows for communication between the user space and the kernel space through system calls made by applications
	- Most modern OS's offer both a GUI and a CLI to enable users to interact with the system, configuration and applications on a device
	- Have 5 main duties:
		- **Process management** - Creates, schedules, prioritises and terminates running programs. Decides how much CPU time each process gets which helps to improve the QoL of multi-tasking
		- **Filesystem management** - Allows for the creation, modification and deletion of files and directories on the filesystem, including the configuration of permissions for files
		- **Device management** - Provides a UI and loads drivers to allow newly plugged in devices to work immediately and make system interaction easier for users
		- **Memory management** - Manages how much RAM each process uses, also provides virtual memory (simulated RAM) using disk space when RAM runs low 
		- **User management** - Separates user accounts and their data/files on a system to prevent different users from seeing another user's data or accessing their account without permission
	- Provide their own security features before the firewall/antivirus, including:
		- System Security - Protects critical system files and processes which are necessary to keep the machine stable and working properly
		- Authentication - Separates different users on a device and requires a login for each to protect individual users' data as well as preventing unauthorised access to users that can make system wide changes i.e. root/administrator
		- Permissions - Prevents unauthorised access/interactions to data depending on user/group permissions on their files, restricting their access or modification from users without the correct permissions
		- Isolation - Keeps the Kernel space and User space separate to prevent apps from controlling hardware. <- makes systems more stable by preventing faulty apps from crashing the system; stops apps from fighting over hardware resources too

- Kernel Space - Where the kernel lives, sits between the OS and hardware. 
	- The kernel can interact with the hardware directly. 
	- Separated from the User space for system stability
- User Space - Where apps and processes exist and run. 
	- Apps must make system calls through the OS to interact with the kernel when needing to use/access hardware resources i.e. playing a video

- Types of Operating Systems - Many exist but all have a different focus/intended purpose such as being built for specific types of devices:
	- Desktop - Usually designed for daily or work use i.e. gaming, editing, file management etc
		- Typically feature a GUI and CLI to interact with and configure the system
	- Servers - Usually designed for data storage and handling, app/service hosting or handling client requests
		- Tend to be headless (no monitor/visual interface) and are usually configured through backend scripting/programming
	- Mobile - Primarily used for mobile and tablet
		- Touch based UI, power efficient, always connected, app sandboxing
	- Embedded and IoT Devices - Used in devices with a dedicated purpose
		- Low footprint, lightweight
	- Virtual and Cloud - Designed for cloud servers/services
		- Lightweight, Scalable, rapid deployment 


- Examples OS's for each are:
	- Desktop
		- Windows - *Windows 7, Windows 10, Windows 11 (current)* - Most popular
		- Linux - *Ubuntu, Debian, Fedora* - family of open-source OS's, typically free
		- macOS - *sonoma (14), Sequoia (15), Tahoe (26)* - Apples own OS used for their devices
	- Server
		- Windows - *Windows Server 2019, 2022, 2025* - used for large data networks, data centres and corporate environments
		- Linux - *Ubuntu Server, Debian, CentOS, Red Hat* - majority of web servers
		- Unix - *IBM AIX, Oracle Solaris* - Large enterprises. often closed-source, proprietary typically need to purchase a license to use unlike Linux
	- Mobile  
		- Android - *Android 14 - 17, manufacturer versions* - Most widely used mobile OS
		- iOS - *iOS 18, 26, 26.5* - Apple's mobile OS for their devices
	- Embedded and IoT devices
	- Embedded Linux - *OpenWrt, Ubuntu Core, Yocto Project* - Specialised OS built into devices with dedicated functions
	- Real-Time OS - *FreeRTOS, VxWorks, QNX* - Used where tasks need guaranteed response times
	- Virtual and Cloud - 
		- Cloud/VM - *Ubuntu LTS, Amazon Linux, Rocky Linux* - Used by large data centres that host cloud services
		- Container-Optimised - *Alpine Linux, Bottlerocket AWS, Flatcar Linux* - Alternative to VMs, package only app and its dependencies <- Lightweight
  