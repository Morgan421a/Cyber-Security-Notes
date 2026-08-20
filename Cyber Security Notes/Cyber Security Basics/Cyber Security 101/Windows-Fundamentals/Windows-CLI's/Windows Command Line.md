**Car Park**
- CLI lower resource usage reason behind servers being headless? 
	- Yes, primarily, also more secure via reduced attack surface (less packages since no GUI means less security holes), also more stable (less services that might crash or hang like with a GUI)
- Reasons for companies to not block ICMP packets?
	- Yes, most companies filter but don't completely block them to avoid causing operational problems
- Need to know server IP for `nslookup` with IP addy?
	- Yes, specifying a server asks the domains specific DNS for the IP; allows for: 
		- Bypassing broken local DNS - internal DNS down or misconfiged, public DNS can be used to verify if the internet is actually working
		- Checking DNS propagation - Website's IP address updates take time to be reflected globally, querying specific DNS servers in different regions allows user to see which ones have the new IP and which still have the old one
		- Testing authoritative servers - "Master" DNS server's IP for a domain can be found (using `nslookup -type=NS`) and used to query that specific server directly; tells absolute truth regarding what the domain's records are, bypassing all caches and lies from intermediate servers
		- Security verification - A trusted external DNS (such as cloudflare's `1.1.1.1` ) can be queried to see if it returns a different IP than the expected DNS. Good if network hijacking (DNS Spoofing) is suspected; e.g. to send users to a fake banking site

#### **Basic Systems Information**
- Commands can only be issued within the **Windows Path**
	- **Windows Path** = An **Environment Variable**; Stores a **semi-colon separated list** of **directories**, typically located on the OS drive, where the OS searches for **executable files**
	- `set` <- Command without arguments displays all current environment variables such as the **Windows path** on the current machine <- indicated by the line starting with `Path=`
- `ver` <- Command used to check the OS version
- `systeminfo` <- Command displays various system info i.e. OS info, system details, processor and memory
- `|` <- Called a pipe
- `<command> | more` <- paginates text output one screen at a time:
	- Page moved forward using `Spacebar`
	- Move to next line using `Enter`
	- Can exit early using `CTRL + C` <- Easier to read large text data outputs such as `systeminfo` or `driverquery`
- `more filename` <- Can be used to display a file
- `help <command>` <- Displays info for a specific command
- `cls` <- Clear prompt screen

#### **Network Troubleshooting**
- `ipconfig` <- Displays network information such as IP addy, subnet mask, and default gateway
	- Also Shows **Link-Local IPv6 Address** <-
- `ipconfig /all`<- Displays more info about the network config such as the DNS servers and the state of DHCP (enabled/disabled)
- `ping target_name` <- Uses ICMP packets to check for a response from a server over the internet; receiving a response = client can reach target and target can reach client
	- Also shows average time for a round trip, how many packets were sent, received, and lost
- `tracert target_name` = *trace route* <- Traces network route traversed to reach the target
	- Uses **ICMP Echo Request** packets with incrementing TTL 
		- Just like `ping`, firewalls can be configured to drop (silently) the packets, resulting in a **Request timed out** one the packet's TTL expires
	- Expects routers on the route to report back if they drop a packet due to its TTL reaching 0
- `nslookup sitename.TLD` <- Returns IP addy of host or domain
	- `nslookup sitenmane.TLD server.ip.address` <- Same as before but queries the specified DNS server
- `netstat` = *network statistics* <- Displays current network connections and listening ports; with no arguments shows established connections.
	- e.g. `TCP  10.10.230.237:22  ip-10-11-81-126:53486  Established`
		- `TCP` - Shows the protocol being used for the connection
		- `10.10.230.237:22` - IP addy and port number of the client machine used in the specific connection; in this case SSH connection cause port 22
		- `ip-10-11-81-126:53486` - IP addy and port number of the remote computer the client's machine is talking to
		- `Established` - Current status of the connection
	- Some `netstat` flags:
		- `netstat -h` <- Displays the help page
		- `netstat -a` <- Shows all established connections and listening ports <- shows listening ports even if they don't yet have a connection
		- `nestat -b` <- Shows program associated with each listening port and established connection i.e. `[badr.exe]` or `[sshd.exe]`
		- `netstat -o` <-  Reveals Process ID (PID) associated with each connection
		- `netstat -n` <- Uses numerical form for addresses and port numbers
			- Skips DNS resolution of `netstat` making output instant; better for real-time snapshot of a busy server
			- Used to troubleshoot network/DNS issues -> if DNS failing, `netstat` may return incomplete data or freeze, `-n` still allows raw IP addies and port numbers to be seen
			- Better for scripting/automation:
				- Hostnames can change but IP addies in specific log snapshots are static 
				- Easier to parse fixed numeric formats
				- Scripts won't fail or slow down using `-n` if network's DNS server becomes unavailable
			- `-n` better for security and precision:
				- forces the display of the actual numeric port: 
					- Helps spot malicious programs running on non-standard ports while spoofing service names
					- Allows for verification of the exact port number
				- DNS records can be poisoned or misconfigured meaning DNS resolution can be misleading:
					- Raw IP addy ensures display of actual destination address
		- All flags can be used together, except`-h`,  for a detailed display of network statistics

#### **File and Disk Management**
##### **Working With Directories**
- `dir` <- List child directories
	- `dir /a` <- displays hidden and system files too
	- `dir /s` <- displays files in current directory and all subdirectories
- `tree` <- Displays a visual representation of the child directories and subdirectories
- `mkdir directory_name` = *make directory* <- Creates a directory with specified name
- `rmdir directory_name` = *remove directory* <- Deletes the specified directory

##### **Working With Files**
- `type filename` <- Displays the contents of the specified file
	- Use should be avoided to display binary files as will show an effectively unreadable string of characters representing control codes used in the binary file
	- `more` command can be piped to display large amounts of content in a paginated format as such `type filename | more`
- `copy` <- Allows files to be copied from one location to another e.g. `copy test.txt test2.txt`
	- Creates new file if destination file doesn't exist
	- Overwrites an existing destination file **Does not append**
		- to append the `+` operator must be used as such:
			- `copy test2.txt + test.txt test2.txt` <- Reads initial destination, appends specified data, then writes the combined result back to the destination:
				- copy -> Destination + copy-file -> Destination
- `move filename destination` <-  Moves a file to the specified location
	- e.g. `move test.txt ..` <- moves `test.txt` up one level
- `del filename` or `erase filename` <- Deletes a file
- A **wildcard Character** `*` can be used to refer to multiple files
	- e.g. `copy *.md C:\Markdown` <- Copies all files with the `md` extension to the directory `C:\Markdown`

#### **Task and Process Management**
- `tasklist` <- lists all running processes as a **point-in-time snapshot**, including their PIDs
	- `tasklist /?` <- displays help page for the `tasklist` command
	- Can find specific tasks using `/FI "imagename eq taskname"` 
		- `/FI` = *Filter*
		- `imagename` <- set the filter to the process executable name
		- `eq` <- equal to (can also be `ne` <- not equal to)
		- `taskname` <- the process executable name to filter
	- example: `tasklist /FI "imagename eq sshd.exe"` <- looks for all tasks related to `sshd.exe`
- `taskkill /PID target_PID` <- kills the process with the specified PID
	- e.g. `taskkill /PID 1516` <- Kills the process with the process ID of `1516`

#### **Extra Commands**
- `chkdsk` = *check disk* <- Checks filesystem and disk volumes for errors and bad sectors
- `driverquery` <- Displays list of installed device drivers
- `sfc /scannow` <- Scan system files for corruption and repairs them if possible
- `/?` <- Can be used with most commands to display a help page
- `shutdown /s` <- Used to shutdown the computer
- `shutdown /r` <- Used to restart the computer
- `shutdown /a` <- used to abort a scheduled shutdown of the computer