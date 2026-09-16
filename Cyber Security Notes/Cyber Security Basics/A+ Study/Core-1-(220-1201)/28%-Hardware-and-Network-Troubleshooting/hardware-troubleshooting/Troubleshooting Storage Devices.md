### Storage Failure Symptoms
- **Read/Write Failure** -> "Cannot read from the source disk" message
	- Cannot write to or read data from the storage drive
	 - Commonly accompanied by slow performance
		 - Drive usually keeps retrying the same area of the drive
	- Often causes an audible clicking noise
		- **"Click of Death"** <- Difficult to recover the data once HDD starts making noise
		- May include grinding or scraping noise

### Grinding Noises
- Hard drives are mechanical, spinning drives (often 5400 RPM and higher)
	- Moving actuator arms allow head to read data
- Very high tolerances, if one component fails it often cascades and causes the other parts to follow suit, causing a complete drive failure
- Clicking or Grinding Noises indicate the onset or occurrence of a failure
	- Metal on metal grinding between components
- Typically results in poor performance, an error message, or no access at all
- Difficult to recover from <- Everything on a system should be backed up frequently to prevent large or critical loss of data

### Troubleshooting Disk Failures
- Get a backup (if possible), especially if grinding, clicking, or scraping noises can be heard
- Check for loose or damaged cables
- Check for overheating <- Drive may be getting too hot to operate properly
	- Especially if problems occur after startup
- Check Power Supply <- Especially if new devices were added
	- Can PSU still provide sufficient power?
- Run Hard Drive Diagnostics
	- Commonly found on drive manufacturer's website or can be built in to computer motherboard
	- Test on a known good computer if possible

### Drive Activity Issues
#### Slow Performance (HDDs)
- Could be caused by fragmentation, bad sectors or ageing components
	- Run disk defragmentation <- HDDs Only -> Fragmentation only affects HDDs, not SSDs
	- Check disk health using built-in utilities
#### Failure to spin up (HDDs)
- Indicates motor failure or insufficient power
	- Check Power connections
	- Test with another power source
#### Limited Write Cycles (SSD)
- SSDs have finite number of program/erase cycles
	- Enable TRIM command to optimise performance
	- Reduce unnecessary write operations
	- Monitor SSD health using manufacturer tools
#### Bad Blocks (SSD)
- SSDs automatically remap bad blocks to spare areas; when spare block runs out, drive failure imminent
	- Monitor drive health using SMART data
	- Back up data before drive failure
#### No Drive activity (HDD and SSD)
- LED light on front panel not blinking during read/write operations
	- Possible faulty power or data cables; Drive may not be recognised in BIOS
		- Check and reconnect cables; Verify drive is detected in BIOS
#### Read/Write Failures (HDD and SSD)
- Error messages such as "Cannot read from Source disk" or "Cannot write to disk"
	- Possible caused by bad sectors (HDD) or bad blocks (SSD); May be a corrupt filesystem
		- Run diagnostics utilities such as `CHKDSK` command (Windows), `fsck` command (Linux)
		- Backup data and replace drive if error continues
#### Drive Troubleshooting Steps
1. Physical Inspection
	- Check power and data connections
	- Listen for unusual noises (HDDs)
	- Feel for vibrations (HDDs should vibrate slightly)
2. BIOS/UEFI Check
	- Ensure drive is detected
	- Verify boot order settings
3. Operating System Inspection
	- Use built-in utilities such as Disk Management (Windows) or `fdisk` (Linux)
	- Check for partition visibility and file system errors
4. Run Diagnostics
	- HDD Tools -> `CHKDSK` Command (Windows), `fsck` command (Linux)
	- SSD Tools -> Manufacturer provided SSD health tools; Enable TRIM and monitor wear levelling

### Boot Failure Symptoms
- Messages such as "Drive not recognised" or Boot Device Not Found"
	- Indicates an issue with the selected boot drive
	- Sometimes lights on the drive indicate when access is attempted <- No lights = drive may be unresponsive
		- Often accompanied by beeps and error messages (if video display is working)
- "Operating System Not Found" <- Drive is available and accessible but no bootable OS is found on the drive
#### Troubleshooting Boot Failures
- Check cables and connections <- Try reseating power and data connectors for the drive
- Check boot sequence in BIOS <- Check BIOS isn't configured to boot from removable disks such as USBs; Check for disabled storage interfaces
- For a newly installed drive, check hardware config <- Ensure Data and power cables are seated properly and not damaged, try using a different known good cable; Try using different SATA interfaces
- Try the Drive in a different computer <- If works, problem may be with SATA interfaces or motherboard

### Data Loss/Corruption
- Hard Drives will inevitably fail at some point
- Repairs are difficult and expensive
	- Not always successful
- SSDs might just stop working
	- Sometimes can read data but not write
- Data may become corrupted or unavailable, thus inaccessible
	- Extremely difficult - impossible to recover from
- ***ALWAYS HAVE A BACKUP***

### RAID Failure
- A drive in a RAID array can fail, potentially due to:
	- Hardware Failure
	- Power Issue <- Maybe not receiving enough power, if at all
	- Communication Issues <- Issue with the connection or cable, etc.
- Most RAID arrays provided detailed info about what's happening, in the form of:
	- Error Messages
	- Email Notifications
	- Audible Alarms
- Requires careful analysis due to the numerous drives and differing volumes to choose from
	- Ensure correct physical drive is the focus of the troubleshooting
#### RAID Recovery
- **Ensure knowledge on which RAID array is being used** (e.g. 0, 1, 5, etc.)
	- **RAID 0** (striping):
		- 2 or more disks
		- Single drive failure breaks the array, with data loss
		- Restore data from backup after replacing bad drive
		- **Regular backups crucial**
	- **RAID 1** (Mirroring):
		- 2 or more disks
		- Array works as long as one drive is operational
			- System operates in degraded state with slower read speeds during single disk failure
		- Replace bad drive and array will rebuild itself with existing information
	- **RAID 5** (Striping with single parity):
		- 3 or more disks
		- All drives need to be operational aside from one
			- Two or more disks failing means data loss
			- System operates in degraded state with slower read speeds during single disk failure
		- Replace bad drive and re-synchronise array
	- **RAID 6** (Striping with double parity):
		- 4 or more disks
		- All drives need to be operational aside from two 
			- Three or more disks failing means data loss
		- Replace bad drive(s) and re-synchronise array
	- **RAID 1 + 0** / RAID 10 (Striped Mirrors):
		- 4 or more disks
		- Can lose one drive per mirrored pair without data loss
		- Replace bad drive(s), array will rebuild itself with existing information

### S.M.A.R.T
- **Self-Monitoring, Analysis, and Reporting Technology**
- Technology used to keep track of stats regarding the performance of a drive
	- Typically use third party utilities to take stats and display them, allowing user to see how drive is performing
- Look for warning signs to avoid hardware failure, indicated by statistics such as:
	- Power_On_Hours
	- Power_Cycle_Count
	- Temperature_Celsius
- Third party software can be used to read the data and perform an analysis
	- Removes the need to manually read and decide if there are any issues
	- May be able to perform analysis overtime such as daily, weekly, or monthly checks to show drive performance overtime
- Once warning signs appear replace the drive before complete failure
	- Helps prevent sudden or catastrophic failure
#### S.M.A.R.T Analysis
- RAID arrays commonly have S.M.A.R.T functionality built-in
	- Third party software on a portable device that only has a single drive in them can be used
- Watch S.M.A.R.T metrics overtime
	- Check for changes or incrementing values
- Often sends automated notifications through different methods such as:
	- Email
	- Text messages
	- Console Notifications
- If issues or concerns arise:
	- Make a backup of the drive
	- Try to resolve the issue if possible
	- Replace the bad drive if needed

### Extended Read/Write Times
- A lot happens when reading/writing data
	- Memory access, communication across the bus, spinning drive access (HDDs), writing or reading the data to the storage device, etc.
	- Can create considerable delay
- Delays can occur at any point during the process
- Performance checks can be used to see which drive is better for a specific application
	- Use metrics such as:
		- **Input/Output Operations per second** (IOPS) <- A broad metric of performance; Overall capabilities of a storage device
			- Example: Hard Drive: 200 IOPS, SSD: 1,000,000 IOPS
			- Drop in IOPS can indicate hardware or software bottlenecks

### Missing Drives in OS
- OS boots normally
	- Other drives not shown <- Check BIOS, may be disabled in BIOS or an error in BIOS
		- Check BIOS logs or BIOS config to check if system can actually see the drives as accessible
- Check Disk Management (Windows) or `lsblk` (Linux)
- Check for power/data cable issues
- Network Shares:
	- Not a physical drive on the computer, rather a drive that's mapped across a network
		- Mapping typically done during startup via a login process or login script
			- User can map drive manually

### Array Missing
- Missing or Faulty RAID controller
- Check Configuration Utility in console to investigate why the controller or drive connected to the controller is having a problem
- Common causes:
	- Disconnected or fault cables
	- RAID controller failure
	- Multiple drive failures
- Troubleshooting:
	- Check connections
	- Replace components
	- Reconfigure array

### RAID Array Troubleshooting Steps
1. Identify Issue
	- Check for RAID controller logs and error messages
	- Listen for alarms and inspect system notifs
2. Check Physical Components
	- Inspect power and data cables
	- Verify drive connections and health
3. Evaluate RAID controller
	- Confirm firmware and driver are up to date
	- Test array with a known working RAID controller if possible
4. Monitor Performance
	- Analyse disk I/O Speeds
	- Check for unusual slowdowns or lagging access times
5. Rebuild the Array
	- Follow manufacturer guidelines to rebuild degraded arrays
	- Monitor rebuilding process to ensure completion

### LED status indicators
- **Constant Blinking** = **Excessive disk activity**, could be due to low RAM, indexing, antivirus scans, background updates, a failing drive retrying reads, etc.
- **No Blinking** = Potential **Power or connection issues**


