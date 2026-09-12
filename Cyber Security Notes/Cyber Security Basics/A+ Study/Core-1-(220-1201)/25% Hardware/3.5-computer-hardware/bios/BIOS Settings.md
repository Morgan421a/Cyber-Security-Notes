### Entering The BIOS
- Launching the system setup during system boot
	- Typically: **Del**, **F1**, **F2**, **F10**, **Ctrl-S**, **Ctrl-Alt-S**
- **Some desktop Hypervisors** allow for the **VM boot** to be **stopped** in order **to enter the BIOS** **for** a **Virtual Machine**
	- **Hyper-V** for **Windows 10/11**
	- **VMware Fusion** for **macOS**
	- **Some Third-Party hypervisors** such as **VMware Workstation**
	- **VirtualBox** **Doesn't support** virtual BIOS config
- Provides config options for hardware, security, clock speeds, boot order, and more

### Fast Startup
- Used for **Windows 10 and 11** (and previous versions)
	- Computer doesn't shut down completely
	- Starts up too fast to open the BIOS configuration
- Hold **Shift** when clicking **Restart** to **shut down completely**
	- Can also use **Settings** -> **Update & Security** -> **Recovery** -> **Advanced Startup** -> **Restart Now**
	- **Temporary changes to fast startup** can be **made within** the **System Configuration** (`msconfig`)
	- If none of the above available or working, **interrupt boot process 3 times in a row**
		- **4th time will boot from very beginning**

### Important Notes
- Making **changes to** a **BIOS** **may result in** a **system not booting** or **not being stable**
	- **Make** a **Backup of previous BIOS config**
	- **Document all changes made** e.g. write them down, take a picture
- **Don't make a change unless certain of the setting**

### Boot Options
- Upon starting, BIOS sees all config settings made for the device
- **Hardware** can be **disabled** **in** the **BIOS** <- **Makes** the **hardware** **unavailable to OS**
- **Configure Boot Order**
	- **Select** which **storage device** **to** try and **boot from first**
		- If first one fails, move to the next option
	- Common devices in the boot sequence are:: HDDs or SSDs, Optical drives, USB devices (e.g. flash drives), and network adaptors (via PXE)
	- Best practices for boot order:
		- Prioritise HDD/SSD containing the installed OS
		- Disable booting from external devices to prevent unauthorised access

### USB Permissions
- **Enable/Disable USB ports**
- **Restrict USB port usage for specific devices**
	- USB ports may need to be restricted, typically for security reasons
		- USB devices tend to be small and some can have very large capacities
- Protects against Malware introduction through USB drives or data exfiltration through USB storage devices
- **USB connections** are both **convenient** and **high-speed**
	- Good for moving data between devices
	- Bad when someone with malicious intent has access to the USB drive
		- US Department of Defense (DoD) banned USB flash media for 15 months in 2008 due to somebody infecting a DoD computer with the **SillyFDC worm** which spread and infected all other systems on the DoD's network

### Fans
- Commonly used as a part of a computer's cooling system
	- CPU fans and Chassis fans
	- Pulls cool air into case for components and towards CPU
- Motherboards tend to include **temperature sensors** and an **integrated fan controller**
	- Motherboard can **detect** **component temperature** and **increase/decrease fan speeds** as needed
	- **Fan controllers configured inside system BIOS**
		- Typically offers multiple preset options, such as:
			- Best Performance - System runs at best possible cooling for the system at the time <- Most flexible
			- Best Experience - Minimises noise made by fans <- quietest but worst cooling
			- Full Speed - Fans always running at full speed <- Best cooling but loudest

###  Secure Boot
- Malicious software can "own" a system
	- Malicious drivers or OS software
- **Secure Boot**
	- Part of UEFI specification
	- Has digital signature for known-good software (e.g. operating systems like windows and macOS)
		- Knows what a specific software should look like <- if any modifications detected, stops the boot process to prevent potential malware from running
		- Cryptographically secure
		- Software won't run without the proper signature
- Support in many different Operating Systems
	- Windows and Linux Support
	- Older OS's may be prevented from running by **secure boot**
#### UEFI BIOS Secure Boot
- **Secure boot checks OS and BIOS**
- UEFI BIOS Protections
	- Looks at BIOS configuration and determines the manufacturer's public key for the particular system <- **Manufacturer's public key included in the BIOS**
	- **Compares public key with digital signature during a BIOS update**
	- If digital signature can't be confirmed with public key, **secure boot prevents unauthorised writes to the flash** <- Prevents any BIOS updates from overwriting current config
- **Secure Boot Verifies** the **bootloader** **before OS starts**
	- Checks **OS bootloader's digital signature**
	- **Compares** digital signature with a **trusted certificate** **or** a **manually approved digital signature**
		- If signature doesn't match, OS won't start

### Boot Password Management
- **Boot Password** / **User Password**
	- Prevents system from booting without valid password
	- Need password to boot to the OS
- **Supervisor**/**BIOS Password**
	- Restrict BIOS changes to those who lack the correct password
	- Must use password to change any configuration settings
- If either password lost, BIOS config must be reset to recover
	- Different reset process between manufacturers <- Check documentation
- **Storage**/**Hard Drive Password**
	- Locks the Hard drive to prevent unauthorised access to its data
#### Clearing a Boot Password
- **BIOS Software and configuration** both **stored** **on** the **motherboard as flash memory**
	- Software stored on flash memory so it can be upgraded if need
- **Complementary Metal-Oxide Semiconductor** (CMOS)
	- Type of memory that used to be used when working with the BIOS
		- Typically done using flash memory nowadays <- Easily stored and accessed
	- **CMOS battery failure causes loss of settings**, such as, system time and date
	- May be **backed up with** a **battery** as **memory was volatile** <- **Flash memory** is **non-volatile**
	- Reset with a jumper <- Short (connect) two pins on the motherboard

### Temperature Monitoring
- Part of the BIOS
	- Built-in diagnostics
- Run from the BIOS menu
	- No need to install additional media or software
- Focused on hardware checks
	- Doesn't touch the OS

### Virtualisation Support
- Run other OS's within a single hardware platform
	- Multiple OS's share physical hardware components
- Virtualisation in software was limited
	- Posed performance and hardware management challenges
- **Virtualisation added to the processor**
	- Hardware is faster and easier to manage
	- **Intel Virtualisation Technology** (**VT**)
	- **AMD Virtualisation** (**AMD-V**)