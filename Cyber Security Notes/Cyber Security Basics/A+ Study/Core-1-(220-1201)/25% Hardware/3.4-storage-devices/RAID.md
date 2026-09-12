**RAID IS NOT A BACKUP**

### RAID
- **Redundant Array of Independent Discs** (RAID)
	- Sometimes called **Redundant Array of Inexpensive Discs**
- **Combines** **multiple physical hard disks** **into** a **single logical disk**
- Different **RAID levels**
	- Some allow for **redundancy**, some don't
	- RAID 0 - Striping
	- RAID 1 - Mirroring
	- RAID 5 - Striping with one parity drive
	- RAID 6 - Striping with two parity drives
	- Nested RAID - RAID 1+0 (AKA Raid 10) - A stripe of mirrors

### RAID 0 - Striping
- **File Parts** (Blocks) **split** **between** two or more **physical drives**, e.g. drive 1 has block 1A, 3A, and 5A, drive 2 has block 2A, 4A, and 6A
- **High performance** <- data written quickly because small pieces of data written to separate drives instead of all of it to one drive
	- Increased Speed
- **No Loss of disk space**, e.g. Two 800 MB discs create 1600 MB of usable space
- **No Redundancy**
	- Any drive failure breaks the Array
	- **RAID 0 is Zero Redundancy**
- Useful for high speed applications (e.g. gaming, video editing)

### RAID 1 - Mirroring
- **File parts** (blocks) **duplicated** **between** two or more **physical drives**
- **High disk utilisation**
	- Since every file is duplicated, **disk space needed** is **doubled**
	- 50% of storage capacity used for redundancy, e.g. two 800 MB discs create 800 MB of usable space (instead of 1600 MB)
- **High Redundancy**
	- Drive failure doesn't affect data availability <- other drive has the same data

### RAID 5 - Striping With 1 Parity Drive
- **File blocks** are **striped** (split between multiple drives) **along with 1 parity block** (can detect and, in some cases, correct errors)
- **Requires at least 3 drives**
	- Data block split across physical drives, one drive stores the parity block not the data block <- Parity distributed across the physical drives to make recovery process more efficient
- **Efficient use of disk space**
	- Files aren't duplicated, but space is still used for parity, e.g. three 800 MB disks create ~1600 MB usable space (one disk used for parity)
- **High Redundancy**
	- In event of drive failure, existing data can be combined with the parity block for that data to re-create the lost data
	- Data available after drive failure
	- Parity calculation may affect performance
	- **Parity based redundancy**

### RAID 6 - Striping With 2 Parity Drives
- **File blocks striped** along with **2 parity blocks**
- **Requires at least four drives**
	- **Extra drive** adds **more parity**, **not extra capacity**, e.g. four 800 MB disks create ~1600 MB usable disc space (two disks used for parity)
- Two drives can be lost but data would still to be available <- Greater redudancy

### RAID 10 (RAID 1+0)
- Combines **RAID 0 and RAID 1**
	- **RAID 0 = Striping**, file blocks split across each drive <- **0 redundancy**
	- **RAID 1 = Mirroring**, each striped set of drives is duplicated <- **Adds redundancy**
- **Requires at least 4 drives**
	- Multiple drives can be lost without losing data
- **Speed of striping** combined with the **redundancy of mirroring** <- A **Stripe of Mirrors**
	- **Redundancy with speed**
- 50% of storage space used for redundancy, e.g. four 800 MB disks create 1600 MB usable disk space (instead of 3200 MB)

### RAID Categories
- **Failure Resistant:**
	- Protects against data loss if a single disk fails
		- RAID 1, RAID 5
- **Fault Tolerant:**
	- Continues to work even if a component (disk or card) fails
		- RAID 1, RAID 5
- **Disaster Tolerant:**
	- Ensures access to data even if half of the RAID array fails
		- RAID 10


