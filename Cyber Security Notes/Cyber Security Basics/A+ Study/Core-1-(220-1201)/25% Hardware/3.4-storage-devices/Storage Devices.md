- Stores data, even when device is off
- Many ways to store data, including:
	- Hard drives
	- Solid-State Drives
	- Flash Drives
	- Memory Cards
	- Optical Drives

### Hard Disk Drives (HDD)
- **Non-volatile, magnetic storage**
	- Uses **rapidly rotating platters** which **store** the **data**
- **Random access** storage **method**
	- Data can be retrieved from any part of the drive at any time
- Uses **Moving parts**, including:
	- Spinning platters
	- Moving actuator arm <- reads and writes info from the spinning platters
	- Head <- Sits on the end of the actuator arm to read and write to and from the platters
	- Spindle <- Central part that spins the drive
- **Mechanical components limit** **access speed and can break**
- Different sizes to suit the device its installed in e.g. 3.5" common in desktops, 2.5" common in laptops and other mobile devices <- size = width of drive
#### Spindle Speeds
- **Higher RPM = lower latency**:
	- 15,000 RPM = 2 ms average rotational latency
	- 10,000 RPM = 3 ms average rotational latency
	- 7,200 RPM = 4.16 ms average rotational latency
	- 5,400 RPM = 5.55 ms average rotational latency

### Solid-State Drive (SSD)
- Non-volatile memory
- **No moving parts** <- Thus solid state
- **Very fast performance** due to no spinning drive delays
#### PCIe Storage Interfaces
- Allowed the throughput of SSDs to be increased by connecting them to the PCIe (PCI express) bus of the computer
	- Commonly done via an adapter card
	- Motherboard provides power
	- PCIe bus allowed for a higher throughput
- PCI Express allowed for speeds up to 64 GB/s per lane
- Used before M.2
### NVMe
- **SATA was designed for hard drives**
	- Uses **AHCI** (Advanced Host Controller Interface) to **move drive data to RAM**
	- **SATA revision 3** had a **throughput up to 6 Gbps**
	- SSDs need a faster communication method
- **NVMe (Non-Volatile Memory express)**
	- Designed for SSD speeds
	- Low Latency
	- Supports **higher throughput since directly connected to PCIe bus**
	- **NVMe using M.2 theoretical transfer speed of 20 Gbps**

### Serial Attached SCSI
- Latest generation of SCSI technology
- **Increased** storage **throughput**
- **Serial communication**
	- **Serial Connection** allows for **speeds up to 22.5 Gbps** for high-end SAS
- **SCSI Protocol**
	- Can be used to control and manage data stored on drives <- Useful in large storage arrays
- **SAS = Serial Attached SCSI**
### mSATA (mini-SATA)
- Useful for laptops and mobile devices
- Same data, just smaller form factor
- Smaller than 2.5" SATA Drives
- No spinning drive allows for different form factors
- Was **used briefly** but **replaced quickly by m.2 standard**
### M.2 Interface
- Smaller Size
	- No SATA Data or Power Cables
- **Can use PCIe speeds since connected directly to system bus**
	- **4 GB/s throughput or faster** when using NVMe PCIe x4
- **Different M.2 Interfaces** support **different connector types**
	- Module needs to be compatible with the slot key/spacer
		- B key, M key, or B and M key
			- Some M.2 drives will support both
#### B-Key and M-Key
- **M.2 doesn't guarantee NVMe support**
	- **M.2 Interface may be using AHCI** <- Check documentation

### Flash Drive
- **Consist of EEPROM** (Electrically Erasable Programmable Read-Only Memory)
- Non-Volatile memory
	- No power needed to retain data
- **EEPROM has a certain number of writes**
	- Will stop writing data to drive after too many writes
		- Data can still be read from the drive just not written to it
- Not designed for archival storage
	- EEPROM limitations
	- Easy to lose and damage
	- Backup of data should always be stored elsewhere
#### Flash Memory
- USB Flash Drives <- Most widely used type
- Compact Flash (CF) <- One of the original types of flash drives
- Secure Digital (SD) <-Often used in mobile devices
- MiniSD <- used in smaller mobile devices
- MicroSD <- used in the smallest mobile devices
- xD-Picture Card <- Typically used for cameras

### Optical Drives
- Disc with small bumps that are read with a laser beam
	- Microscopic binary storage
- Relatively slow due to reading using a laser
- Many Different formats, e.g. CD-ROM, DVD-ROM, Blu-ray
- Optical Drive readers can be internal and external