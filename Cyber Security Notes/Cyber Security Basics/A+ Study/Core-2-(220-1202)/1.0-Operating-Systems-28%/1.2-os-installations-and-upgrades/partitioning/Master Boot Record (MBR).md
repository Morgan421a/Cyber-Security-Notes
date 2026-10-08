- MBR = Old partition style with limitations
	- **Max partition size = 2 TB**
	- **Partition information stored in** **first 512-byte sector** **of** **disk**
- Commonly used for legacy systems
- **Two types of partitions**, **Primary** and **Extended**
#### Primary Partition:
- **Bootable partitions** <- OS must be installed into one of the primary partitions
- **Max of 4 primary partitions per storage drive**
- **Only** **one** of the **primary partitions** can be marked as **Active**
	- Active partition = The bootable partition
	- If wanting to boot from different primary partition, active partition must be changed in computer's partitioning software
#### Extended Partition:
- Used to **extend max number of partitions** on a storage drive
	- **One extended partition per storage device**
	- **Optional**, doesn't have to be installed
- Additional logical partitions can be created within the extended partition
- **Logical Partitions within extended partition are not bootable**