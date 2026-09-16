### POST (Power On Self Test)
- Firmware (UEFI/BIOS) tests major system components before booting the OS
	- Checks essential hardware components such as:
	- CPU
	- Memory (RAM)
	- Input devices (keyboard)
	- Output devices (Video display)
- Boot process stopped if critical failures identified
- Failures/Issues indicated via audible beep codes through internal speaker or messages on the display
	- Differs between BIOS versions <- Check documentation
		- Don't bother memorising beep codes
#### Common Post issues and troubleshooting
- **No Beep Codes** (No Power):
	- Possible causes:
		- Faulty PSU
		- Motherboard Failure
		- Loose power connections
		- Faulty internal speaker
	- Troubleshooting:
		1. Check power connections
		2. Test PSU using a PSU tester
		3. Inspect motherboard for damage
		4. Test System with a known working PSU
- Continuous Beep (Memory Issue):
	- Possible causes:
		- Faulty or improperly seated RAM
		- Incompatible memory modules
		- Memory controller failure
	- Troubleshooting:
		1. Reseat RAM modules
		2. Test one RAM module at a time in different slots
		3. Replace RAM if needed
- Repeating Short Beeps (Motherboard/Power Issue):
	- Possible causes:
		- Motherboard failure
		- Insufficient power from PSU
	- Troubleshooting:
		1. Check PSU output voltages
		2. Inspect motherboard for visible damage
		3. Reset BIOS Settings
- 1 Long beep + 2 or 3 Short beeps (Video Adaptor Issue):
	- Possible causes:
		- Faulty or improperly seated GPU
		- No integrated video output 
		- Incompatible video adaptor
	- Troubleshooting:
		1. Reseat GPU
		2. Test with a known working card
		3. Use onboard video (If available)
- 3 Long Beeps (Keyboard Issue)
	- Possible causes:
		- Keyboard not connected or defective
		- Stuck or held-down key
		- Faulty Keyboard Controller
	- Troubleshooting:
		1. Disconnect and reconnect keyboard
		2. Clean sticky keys
		3. Test with a different keyboard
- Manufacturer Specific Beep codes:
	- POST beep codes differ between manufacturers such as:
		- AMI BIOS, Award BIOS, Phoenix BIOS
	- Check motherboard documentation for specific beep code meanings
#### POST and boot
- Blank screen on boot but audible beeping noises
	- Usually indicates an issue with:
		- Bad Video on the motherboard
		- Bad Memory
		- Bad CPU
		- Could also be a BIOS config issue for the video subsystem
			- Double check BIOS config
- BIOS time and setting error message
	- Usually indicates:
		- Issue with the (CMOS) battery on the motherboard
			- Replace the battery
- Attempts to boot to incorrect device
	- Set boot order in BIOS config
	- Confirm startup device has a valid OS
	- Check for media connected to startup device (e.g. USB) <- If none detected, BIOS will move to next device in boot order

### Crash Screens
- Occur when an OS experiences a critical failure that prevents it from working properly
- Different ways to handle and display crash errors between Operating Systems:
	- Windows -> **Windows Stop Error** / **Blue Screen of Death** (BSOD)
	- macOS -> **Pinwheel of Death** (Spinning beach ball)
	- Linux -> **Kernel Panic**
##### Windows - BSOD
- Appears when Windows encounters a critical system error
	- Indicates issue OS can't recover from
	- Displays error info, e.g. stop codes and QR codes
- Common causes:
	- Hardware failure -> Faulty RAM, overheating components, failing hard drives
	- Driver Issues -> Corrupt or incompatible drivers
	- Software Conflicts -> System updates, faulty app, malware
	- Overclocking -> Unstable system settings
- Troubleshooting:
	1. Read stop code on screen
	2. Scan QR code for more details
	3. Go to windows.com/stopcode for more info about error
	4. Check Event Viewer for additional info
	5. Update or roll back device drivers
	6. Test system memory and storage using built-in diagnostics
	7. Boot into Safe Mode and troubleshoot recent changes
- Common Stop Codes:
	- CRITICAL_PROCESS_DIED <- Essential process failure
	- SYSTEM_THREAD_EXCEPTION_NOT_HANDLED <- Driver related error
	- IRQL_NOT_LESS_OR_EQUAL <- Interrupt request conflicts
	- VIDEO_TDR_TIMEOUT_DETECTED <- GPU failure
	- PAGE_FAULT_IN_NONPAGED_AREA <- Memory Corruption
	- DPC_WATCHDOG_VIOLATION <- System wait timeout exceeded
##### macOS - Pinwheel of Death
- Occurs when macOS experiences a process failure or becomes unresponsive
	- Displayed as a spinning, multicoloured beach ball
	- No specific error codes provided
- Common Causes:
	- Application hangs
		- Software freezing or using too many system resources
	- Hardware issues:
		- Failing storage, insufficient memory
	- Resource Overuse:
		- Too many apps running simultaneously
	- Corrupt system files
		- OS instability
- Troubleshooting:
	1. Force quit unresponsive app using `cmd` + `Option` + `Esc`
	2. Monitor system performance using Activity Monitor to identify resource-heavy processes
	3. Restart the MAC and check for macOS updates
	4. Run Disk Utility to check for filesystem errors
	5. Reset NVRAM/PRAM and SMC (System Management Controller)
##### Linux - Kernel Panic
- Occurs when Linux encounters an unrecoverable error
	- Displayed as a black screen with white text containing diagnostic data
- Common causes:
	- Kernel Module Issues:
		- Incompatible or faulty kernel drivers
	- Hardware failures:
		- Memory, CPU, or Disk Failures
	- Filesystem Corruption:
		- Damaged partitions or storage devices
	- Resource Conflicts
		- Insufficient system resources
- Troubleshooting:
	1. Note hexadecimal error code
	2. Check system Logs via `journalctl` or `dmesg`
	3. Boot into recovery mode or use alive CD for diagnostics
	4. Update kernel and drivers
	5. Test hardware components using built-in tools
	6. Examine recent system changes, e.g. software updates or config changes
- Common hexadecimal Exit Codes:
	- 0x00000000 - Normal Termination
	- 0x00000001 - General Error
	- 0x00000005 - Input/Output Error
	- 0x0000000C - Out of memory
#### Bluescreens and Shutdowns
- Startup and Shutdown Blue Screen of Death (BSOD)
	- Issue likely related to something OS is unable to recover from, such as:
		- Bad Hardware, Bad Drivers for Hardware, Bad Application
	- If issue only occurred after making a change or installing a new application:
		- Option to use the Last Known Good Config may be given during startup
		- Run System Restore to go back to a specific date and time
		- Rollback the most recently installed driver
	- If issue occurs when starting the computer:
		- Try starting system in Safe Mode
	- If hardware related:
		- Re-check, Reseat, or Remove (if possible) installed hardware such as memory and adaptor cards 
			- Ensure proper connections and compliance with hardware manufacturer's instructions
		- Run hardware diagnostics
			- Typically Provided by motherboard or hardware component manufacturer
			- BIOS may have built-in hardware diagnostics <- Typically allows for the selection of a specific component and how thorough a check should be done
#### Proprietary Crash Screens
- Windows BSOD specific to Windows System
- Every app running on a system may have its own notifications/crash screen
	- Some provide a lot of info and state the exact issue/troubleshooting steps
		- Others provide little information and may just state an error number and short error such as "Framebuffer not supported", with no troubleshooting steps
- As much crash information as possible should be documented as a technician or user seeking help 
	- Quality of information contained in help desk tickets can vary; as much detail as possible should be provided
	- Detailed transcript of error is valuable
		- Screenshots are even better
			- Help desk ticket instructions can ask for a screenshot when creating a ticket

### Blank Screen
- First check if monitor is connected properly
	- Check both power and signal cable
- Check input selection on monitor, some have multiple all in one
	- HDMI, DVI, VGA, etc.
- Image is dim:
	- Check Brightness controls
- Swap the monitor:
	- Try the problem monitor on another computer
		- If monitor works on another computer, issue unlikely related to monitor hardware
	- Try a known, good monitor from another computer
		- If monitor screen still blank, issue unlikely related to monitor hardware
- No video after Windows Loads:
	- Information can be seen on screen during boot process but disappears as soon as Windows loads
		- Potentially related to video config inside of the Windows OS
		- Use VGA mode (`F8` during boot process) <- Generic Video Driver

### Power Issues
- Common issue when troubleshooting a computer that won't power on
- Check system regularly and use preventative measures such as surge protectors and auto voltage sensing PSUs to ensure system safety and reliability
- **6 Primary causes**:
##### Power button not properly connected to motherboard
- Power button must send electrical signal to motherboard to boot system
- Symptom = Pressing power button results in no response from system
- Troubleshooting:
	1. Unplug computer from power source
	2. Open case and find power button connection to motherboard
	3. Ensure power button cable securely connected to motherboard
	4. Reseat connection if needed
##### Faulty or inadequate power from power source
- System won't power on if wall outlet (socket) fails to provide adequate voltage
- Symptom = No power to computer despite a connected power cable
- Troubleshooting:
	1. Use Multimeter or voltmeter to test power source
		- NA reading should be 110-120V AC at 60Hz
		- EU/AS reading should be 220-240V AC at 50Hz
	2. Connect red (positive) and black (negative) leads to correct outlet terminals
	3. If voltage is incorrect or absent, test different outlet or call an electrician
##### Faulty Power Cable from Wall to Computer
- Power cables can become frayed or broken overtime, leading to power delivery failure
- Symptom = No power or intermittent power issues
- Troubleshooting:
	1. Disconnect power cable from wall and computer
	2. Use multimeter to check continuity by testing positive pin, negative pin, and ground pin
	3. Expected reading should be 0 ohms or close to 0
	4. If reading shows infinite ohms or high resistance, replace power cable
##### Faulty Power Supply (PSU)
- PSU converts high-voltage AC to low-voltage DC used by computer components
- Symptoms = System fails to power on or shuts down unexpectedly; burning smell or unusual noises from PSU
- Troubleshooting:
	1. Use PSU tester to verify output voltages
		- Expected voltages are 12V DC, 5V DC, 3.3V DC <- acceptable tolerances such as 11.9V to 12.1V are ok
	2. If values significantly off from expected, replace PSU
	- ***NEVER ATTEMPT TO OPEN PSU DUE TO RISK OF HIGH-VOLTAGE SHOCK***
##### Faulty Internal Power Cables (From PSU to Components)
- Faulty cables can prevent components from receiving power
- Symptoms = Certain components no receiving power
- Troubleshooting:
	1. Disconnect and inspect cables for visible damage
	2. Use multimeter to test continuity across cable
		- Should be 0 ohms or close to 0
	3. Replace cables if any individual wire is faulty (Assuming modular PSU)
##### Incorrect Voltage Setting on PSU
- Some older PSUs have a manual switch to set voltage based on the region
- Symptoms = No power if set to wrong voltage; potential damage if voltage too high for chosen setting
- Troubleshooting:
	1. Check voltage selector on back of PSU, ensure correct setting
		- 115V (NA)
		- 230V (EU/AS)
	2. Switch to correct voltage and test system
- No power at source
	- Use multimeter to check AC power from outlet (socket)
- No power along cable
- No power from power supply
	-  Use multimeter to check DC power from power supply
- Some components working, others aren't (e.g. fans spinning but no other power or lights)
	- Trace back working components to where they're connected
		- Connected directly to power supply or power sources on motherboard
	- Fans spinning but no video <- Likely a POST error = Motherboard or video card could be bad
	- Just fans spinning = Potential issue with voltage sent from Power Supply
		- Fans have lower voltage requirement
		- Use multimeter, check all voltage outputs on Power Supply to ensure all working properly

### Sluggish Performance
- Commonly caused by:
	- Hardware Related:
		- Insufficient RAM -> Upgrading RAM may improve performance but only if existing memory is fully utilised
		- Overheating -> Causes CPU and GPUs to throttle to prevent damage; faulty temperature sensors can falsely trigger throttling <- Check for system slowdowns, automatic shut downs, continuously high fan operation
		- Hard Drive Performance -> HDDs with lower RPMs are slower than SSDs; fragmentation in HDDs can degrade performance
		- Network Bottlenecks -> Congestion or incorrect config can prevent a network adaptor from reaching its full speeds
	- Software Related:
		- OS Misconfigs -> Over-provisioned pagefile (Windows) or swap space (Linux) causing excessive disk usage; incorrect background services consuming system resources
		- App Specific Issues ->  Poorly optimised or outdated apps causing high CPU/memory usage; Running resource intensive apps without sufficient system resources
		- Malware and Unwanted Programs -> Background process consuming CPU, RAM, and storage <- Check for high disk usage, sluggish response, unexpected pop-ups
#### Diagnosing Performance Issues
- Using System Monitoring Tools:
	- Windows:
		- Task Manager -> Check for high CPU utilisation and I/O transfers from apps
		- Resource Monitor -> Locate specific processes causing bottlenecks
		- Performance Monitor -> Analyse long-term performance trends
	- macOS:
		- Activity Monitor -> Check CPU, Memory, and Energy usage
	- Linux:
		- `top` and `htop` commands -> For monitoring real-time resource usage
		- `iostat` -> For disk performance analysis
- Manual Inspection Techniques:
	- Thermal Inspection -> Check heat build up by touching the computer; Listen for loud fan noises indicating thermal load issues
	- Visual Inspection -> Verify proper cable and component seating; Check for dust accumulation is cooling systems
#### Common Fixes for Performance Issues
- Hardware Solutions:
	- RAM Upgrades -> If current RAM usage consistently reaches high levels
	- Storage Upgrades -> Switching from HDD to SSD for faster data access
	- Cooling Optimisation -> Cleaning Dust, Replacing Thermal Paste, or improving airflow
	- Check Disk Space for available space
	- If OS on a hard drive, can try running a **defrag** <- Defragments Hard Drives which reorganises files so they're all lined up and easier for drive to read
		- SSDs are "**trimmed**" <- essentially tells drive where it can safely do cleanup work when it's not busy doing more important things (i.e saving or loading files) 
			- ***SSD DEFRAG MUST NOT BE DONE MANUALLY USING TRADITIONAL METHODS AS IT REDUCES LIFESPAN WITHOUT PERFORMANCE BENEFITS, USE TRIM OPTION IN WINDOWS DEFRAGMENTATION TOOL***
	- Check Power Settings on Laptops -> Laptops may be using power saving mode
		- Throttles the CPU to reserve battery when not connected to a power source
			- Change/disable power saving mode
			- Connect laptop to power source
- Software Solutions:
	- Optimising System Settings -> Adjusting pagefile or swap space to appropriate values; Disabling necessary startup programs and background processes
	- Software Updates -> Keeping OS and drivers updated; Applying patches to resolve known software inefficiencies
	- Perform Anti-virus/Anti-malware scan -> Ensures no malicious software executing in the OS

### Overheating
- Computers generate a lot of heat
	- CPU,s video adaptors, memory, etc
- Common cooling systems include:
	- Fans and airflow
	- Heat sinks on top of components
	- Keep fans clean and ensure no obstructions inside of case
		- Obstructions may limit how much air can be pulled into a system
		- Dust makes it more difficult to keep system cool
- Verify temperature using built-in sensors inside computer alongside monitoring software
	- Software sometimes built into the BIOS by motherboard manufacturer
	- Third party software such as HWMonitor
- Check liquid cooling pumps and radiators are properly installed, have no leaks and sufficient coolant levels
- Close resource heavy apps when not in use
- Ensure good airflow in and around computer with no obstructed vents

### Smoke and Burning Smell
- Often indicate electrical problems such as component failure
- Always disconnect power ASAP
	- Limits scope of damage associated with issue
- Once smoke cleared, locate bad components
	- **Caution: damaged components and their surroundings may be very hot**
	- Replace all damaged components

### Random Shutdown
- No warning or messages, system just shuts off
- Check hardware
- Try starting system up again and check Windows Event Viewer for messages written to event log prior to system shut down
- Commonly caused by heat-related issues
	- Temperature sensors can cause system shut down if any component temperature gets too high to prevent damage to hardware
	- Check all fans and airflow in system
	- Ensure all heat sinks on components are connected and have sufficient thermal paste
	- Check BIOS to see fan status and component temperature
- May be related to failing hardware
	- Check any newly installed hardware or drivers
	- Check Windows device manager <- Has anything been disabled
	- Run hardware diagnostic check <- Ensure no issues with installed hardware
- Cause can be relatively random
	- Difficult to troubleshoot
	- Troubleshoot via process of elimination to shorten list of potential causes

### Application Crashes
- App stops working, may provide an error message or just disappear
	- Check Windows Event Viewer or app specific logs 
		- Check with app manufacturer to see if app logs exist or if any can be turned on for future issues
	- Check Windows Reliability Monitor:
		- Shows a history of application problems overtime
		- Checks for resolution
		- Integrates into event viewer <- Helps filter down information faster
	- Reinstall the Application
		- Ensures latest version is being used and all app components are installed without any error messages
		- If issue persists, issue likely not related to app installation
	- Contact Application support

### Unusual noises
- Computers should hum
	- Not grind or rattle
- Rattling:
	- Usually indicates something has come loose within computer
		- Commonly occurs with heat sinks; remove, reapply thermal paste, and re-install
		- Re-seat component, ensuring proper installation
- Scraping:
	- Typically indicates a Hard Drive issue
- Clicking:
	- Often and issue with the fan (Especially if clicking is methodical)
		- Potentially foreign object in fan path
		- Clean dust and any other debris from fans
- Pop:
	- Usually indicates a blown capacitor
		- Commonly accompanied by visible smoke or smell of smoke
	- Blown capacitor almost always means the hardware needs to be replaced
	- Check capacitors regularly for bulging or signs of damage
- Grinding:
	- Broken or degraded fan bearings

### Capacitor issues
- Capacitors store and regulate electrical charge for smooth power delivery
- Commonly damaged from overheating, ageing, or manufacturing defects
- Signs of damage include:
	- Swelling or bulging -> Indicates impending failure
	- Leaking -> Sour, rancid smell and visible residue
	- Burning Smell -> Caused by a short circuit within the capacitor

### Inaccurate System date/time
- Motherboard battery likely failed -> CMOS Battery, AKA, RTC Battery (Real-Time Clock)
	- Often a "button" style battery (Coin battery e.g. CR2032)
- Bad battery will require a BIOS config or date/time config on every boot
- Older systems can reset the BIOS config by remove the battery
	- Modern computers use a jumper to reset the BIOS config , removing battery won't reset BIOS config
	- Modern Systems use Non-volatile RAM (NVRAM) instead of CMOS for storing BIOS/UEFI settings
		- NVRAM saves settings without constant power
- Accurate System Time crucial for network security, file management, and software operations
