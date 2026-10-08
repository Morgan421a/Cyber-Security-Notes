- Once a partition is created to install an OS, it must be formatted in order to store data on it
	- In other words -> Each partition must be formatted with a file system
		- File systems determine how data is stored and accessed
		- Chosen File system must be compatible with the OS
- **Two ways** to format a partition **in Windows**, **quick format** and **full format**
### Quick Format
- Creates a new file table on the partition
- Effectively erases file system table as if no data was ever installed on a particular drive
	- Looks like data is erased but it's not <- Data could technically be recovered using software as such quick format isn't ideal for secure installations
- Doesn't make any additional checks
	- e.g. no physical checks of the storage drive
- Quick format = default setting during Windows 10 and 11 installation
	- Use `diskpart` for a **full format**
### Full Format
- Writes zeros to the whole disk <- Essentially erases all previous data
	- Data is unrecoverable <- More secure than quick format
- Time consuming:
	- Checks disk for bad sectors
	- Needs to go through entire drive to write the information

### File Systems
- **NTFS** <- Default Windows file system; Not natively readable by Linux or macOS
- **exFAT** <- Compatible with Windows, macOS, and Linux; ideal for external drives and shared storage
- **ReFS** <- Designed for Windows server environments; offers self-healing and fault tolerance
- **APFS** <- Default file system for macOS, iOS, and iPadOS; optimised for SSD performance and security
- **HFS+** (Hierarchical File System Plus) <- Older macOS file system before APFS
- **ext4** <- Default for most Linux distros, offers high performance and journaling capabilities
- **XFS** <- Used for large-scale storage and high-speed performance
- **Btrfs** (B-Tree File System) <- Supports advanced storage features and snapshot capabilities