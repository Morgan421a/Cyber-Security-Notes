**Car Park**

**Inside a Computer System**
- **CPU (Central Processing Unit)** - The brain, executes instructions and calculations - more **cores** = more potential for parallel processing. Connect by the CPU slot on the mobo
-  Motherboard - The Skeleton and Nerves - holds and connects all the other parts together
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

