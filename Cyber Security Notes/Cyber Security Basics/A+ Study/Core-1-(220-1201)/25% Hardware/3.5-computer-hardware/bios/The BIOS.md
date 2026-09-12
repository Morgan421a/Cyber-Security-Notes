### BIOS - Basic Input/Output System
- **Software used to start a computer**
	- Sometimes referred to as the **Firmware**/**System BIOS**/ **ROM BIOS**
		- **ROM** (Read Only Memory) typically not used anymore to **store** the **BIOS software** 
		- **BIOS Software now usually stored** **on** the **motherboard** in **flash memory**
- Initialises the CPU and memory <- Preps everything to run with the computer's operating system
- BIOS power on process called **POST** (Power-On Self Test)
	- **Diagnostic Sequence** to **verify** the **functionality** **of essential hardware** **during startup**, such as: CPU, installed memory, certain peripherals (e.g. keyboard and mouse)
		- Any issues initialising core systems will lead to an error message on the screen
	- Typically only takes a few seconds
- After **POST** is complete, BIOS looks for a boot loader to start the OS from
	- Selected from a user defined hierarchy
	- Depending on setup, may prompt user to select their desired OS from those installed
 ![[Pasted image 20260906072542.png|382]]
 - BIOS Flash Chips on a motherboard
	 - M_BIOS = Main BIOS
	 - B_BIOS = Backup BIOS
		 - Having two allows BIOS to be upgraded while having a fallback option should something go wrong during the upgrade process
- **Manages Data flow between OS and hardware devices**

### Legacy BIOS
- Original/Traditional BIOS that's been around for 25 years
- **Older Operating systems talked to hardware through the BIOS** 
	- Instead of accessing hardware directly
- Has **Limited hardware support**
	- **Lacks drivers** for modern network, video, and storage devices
- **Text-based** <- Uses keyboard to select and change settings

### UEFI BIOS
- **Unified Extensible Firmware Interface**
	- Based on Intel's **EFI** (Extensible Firmware Interface)
- Commonly used for **modern computers**
- A **Defined standard** <- Similar functionality between manufacturers
- Designed to **Replace** the **legacy BIOS**
	- **Graphical and Text-Based** <- Keyboard and mouse can be used to interact with settings
	- Need a modern BIOS for modern computers
- 64-bit support
- Support for storage devices larger than 2.2 TB
- Faster Boot times