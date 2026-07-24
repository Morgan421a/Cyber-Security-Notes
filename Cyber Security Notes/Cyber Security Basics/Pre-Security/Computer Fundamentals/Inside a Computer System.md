**Car Park**

**Inside a Computer System**
- **CPU (Central Processing Unit)** - The brain, executes instructions and calculations - more **cores** = more potential for parallel processing. Connect by the CPU slot on the mobo
-  **Motherboard** - The Skeleton and Nerves - holds and connects all the other parts together
- **RAM (Random Access Memory)-** The Speedy short term memory - Holds data the CPU needs quick access to, volatile so once power goes of all stored data is gone.
	- Modern modules use technology such as DDR5 and DDR6 for faster speed and better performance
	- Connected by **RAM slots** on the mobo (**DIMM**)
	- Most systems require matching pairs of sticks
- **Graphics Card (GPU)** - The Cortex - Receives info from the OS and programs then outputs processed visual data to a monitor. Connected by **PCI Express slots (PCI-E)** on the mobo
- **Power Supply (PSU)** - The heart and lungs - Supplies power to all system components. Distributes power through various connectors such as the main mobo and **molex** connectors.
- **Storage (HDD/SSD)** - The Long-Term Memory - Saves data long term even if powered of unlike the RAM. Connects via **SATA** cables or **PCI Express slots (PCI-E)**
	- **HDD** - Uses physical parts limiting performance but have larger capacity at a lower cost
	- **SSD** - No moving parts, uses memory chips allowing for much faster speeds but are more expensive
- **Network Adaptor** - The vocal cords - Allows computers communicate with other systems. Can be wireless or wired, typically embedded in the mobo but can be added as **expansion cards**. Usually connect by **PCI-E** ports.
- **Input/Output** - The Senses - Receives information to then act on (like humans and stimuli). Commonly connected via **USB, HDMI, Display Port** plugged into the **rear I/O ports**
	- Input - Keyboard, Mouse, Mics, Scanners, etc
	- Output - Monitors, Printers, Speakers, etc


**Power on Process**
1. **Power button** - Sends signal to PSU to allow power flow
2. **Firmware starts** - Allows system components to start up - Done by a central system called Unified Extensible Firmware Interface (UEFI) 
	- UEFI does the same as BIOS but has mainly replaced it
3. **Power-on Self Test** - UEFI tests every component is present, configured correctly and functioning
4. **Select Boot Device** - UEFI goes through an ordered priority list to find the boot up routine for the OS
5. **Initiate Bootloader** - Bootloader is initiated on the selected boot device. Bootloader transfers OS from boot device to the RAM. Once OS is transferred UEFI gives control of components over to the OS.

## **Summary**
- Inside a computer system:
	- **Central Processing Unit (CPU)** - Executes instructions and calculations, more cores = more calculations can be done simultaneously
		- Resides in the CPU slot on a motherboard
	- **Graphics Processing Unit (GPU)** - Converts data from the Operating System and applications into images displayed on the monitor. 
		- Connect via (PCI-E) slots on the motherboard
	- **Random Access Memory (RAM)** - Temporarily stores data needed for tasks the CPU is currently working on. 
		- Volatile = If computer is powered off, stored data on RAM is lost
		- Connects via RAM slots on the Motherboard (AKA DIMM slots)
	- **Power Supply Unit (PSU)** - Provides power to all other components
		- Connects to components via molex cables or the motherboard itself in order to distribute power
	- **Storage Device (SSD or HDD)** - Used for long-term data storage unlike RAM, does not lose stored data when computer is powered off
		- Can be internal or external, connects to motherboard via SATA cables or PCI-E slots
			- **Solid State Drive (SSD)** - No moving parts, uses chips instead of a disk, more expensive for higher storage but tends to be read faster than a HDD
			- **Hard Disk Drive (HDD)** - Uses moving parts such as a disk and mechanical arm to read the disk, cheaper for higher storage but much slower than SSD due to mechanical read time
	- **Motherboard (mobo)** - Board which holds all of the components via various slots 
		- Also allows for power distribution to components that aren't directly connected to the power supply through copper traces embedded within the board's layers
	- **Network Adaptor** - Also known as a Network Interface Card (NIC), sits on the motherboard and allows for networking capabilities by providing a MAC Address. 
		- Usually built into the mobo itself but can be bought as an expansion card
		- Typically connect via PCI-E slots
	- **Input/Output (I/O) Devices** - Devices that can be plugged into the motherboard, typically via the slots on rear I/O panel, to provide and receive data to the system.
		- Example Input devices: Mouse, Keyboard, Microphone etc.
		- Example Output devices: Monitor, Headphones, Printer etc.
		- Typically connect using USB, HDMI, Display port etc.

- Power on Process:
	1. User presses the power button which sends a signal to the PSU to allow power to flow to other components.
	2. Unified Extensible Firmware Interface (UEFI)/BIOS starts and initialises the system's components.
		- UEFI largely functions the same as the older BIOS which it has mostly replaced
	3. UEFI runs checks on each component to ensure they are present, configured correctly and functioning
	4. UEFI checks the configured boot priority list to find the boot up routine for the OS
	5. Bootloader is initialised and transfers the Operating System from the boot device onto the RAM for startup
	6. Operating System starts and the UEFI hands control of components over to the OS