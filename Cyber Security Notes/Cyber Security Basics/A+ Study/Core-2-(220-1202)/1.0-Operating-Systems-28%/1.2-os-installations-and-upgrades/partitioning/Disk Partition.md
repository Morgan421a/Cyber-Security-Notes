- Separates a physical drive into logical pieces
	- Keeping data separated can be useful
	- Multiple partitions not always necessary
- Useful for maintaining separate OS's (Windows, Linux, etc.)
	- Part of a drive partitioned solely for Windows
	- Another part of the same drive partitioned solely for Linux
- Microsoft Calls formatted partitions **Volumes**

### Disk Partitioning
- First step when preparing disks for installing an OS
	- Some drives may already be partitioned
		- Existing partitions may not be compatible with an OS and need to be removed/changed prior to use
- MBR-style hard disk can have up to 4 partitions
- GPT supports up to 128 partitions
	- UEFI BIOS required
- **CREATING AND REMOVING PARTITIONS CAN EASILY DELETE DATA, ENSURE CORRECT DRIVE IS SELECTED AND EXISTING PARTITIONS ARE NOT MODIFIED BY ACCIDENT**