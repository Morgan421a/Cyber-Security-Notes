**Car Park**

#### **Additional Commands**
- `grep [pattern] [values] <filename>` <- Search contents of files for specific values
	- `-R` <- recursive search -> searches all instances of the pattern/value in the specified directory and its sub folders

- `<command> --help` <- Shows all possible options the specified command accepts and a short example of how to use them

- `touch <filename>` <- Create a file (full file path can be provided)

- `mkdir <dir_name>` <- create a directory (full file path can be provided)

- `cp <existing file/dir_name> <copy's file/dir_name>` <- copy a file or directory (full file path can be provided)

- `mv <file/dir_name>` <- move a file or directory; also used to rename files/directories (full file path can be provided)

- `rm <file/dir_name>` <- remove a file or folder (full file path can be provided)
	- `-R` <- flag must be used when removing directories

- `file <filename>` <- determine the type of a file (full file path can be provided)

- `wget <file address>` <- Allows file download from the web via HTTP

- `scp <filename> <target host ssh details>` <- Secure copy - used to securely transfer files between two computers using the SSH protocol
	- command order can be reversed to copy a file from a remote computer that you're not logged into
#### **Shell Operators**
- `&` <- Allows commands to be run in the background of the terminal -> allows terminal to be used while another process/command is running
- `&&` <- Allows multiple commands to be combined together in one line -> command 2 will only run if command 1 was successful
- `>` <- Redirector - Take output from a command (i.e. cat to output a file) and direct it elsewhere -> Can be used to create files or overwrite the data of existing ones
- `>>` <- same as `>` but appends output instead of overwriting existing data

#### **File Permissions**
- `ls -l` <- used to list more info about files in a directory including the permissions for each
	- i.e. rwxrwxrwx <- `r` = read, `w` = write, `x` = execute
		- each group of three represents who the permissions apply to in order of: owner, group, others
		- Each permission has a numeric value
			- `r` = 4
			- `w` = 2
			- `x` = 1
				- numeric value for each group of perms can be calculated by adding all of the permissions together for each, foe example:
					- Owner = `rwx` = 4 + 2 + 1 = 7
					- Group = `rwx` = 4 + 2 + 1 = 7
					- Others = `rwx` = 4 + 2 + 1 = 7
					- So in this case: `rwxrwxrwx` = `777`
			- `-` <- indicates a lack of permission to do something, for example:
				- `rwx------` = `700` <- only the owner has access

#### **Common Directories**
- `/etc` <- Commonly stores system files used by the OS
- `/var` <- short for `variable data`, one of the main root directories on linux
	- stores data that is frequently accessed or written to by services or apps running on the system e.g. log files from running services and apps or other data that's not necessarily associated with a specific user
- `/root` <- home directory for the root user
- `/tmp` <- short for `temporary` - unique root directory for linux, volatile and used to store data that only needs to be accessed once or twice -> clears when computer is restarted
	- any user can write to, so good place to store enumeration scripts and the like once a machine has been accessed

#### **Terminal Text Editors**
- Nano - accessed via `nano <filename>` 
	- `^` symbol = Ctrl

- VIM

#### **Serving files from host - WEB**
- Python provides a module called "HTTPServer" <- turns computer into a simple web server that can be used to serve files, where they can then be downloaded by another computer using commands such as:
	- `curl`
	- `wget http://<website address or server IP>/<filename>`

- `python3 -m http.server` <- starts the HTTPServer

#### **Processes 101**
- `ps` <- lists running processes on a user's session including their PID
- `ps aux` <- lists processes run by other users as well as those that don't run from a session i.e. system processes
- `top` <- real time view of currently running processes, refreshes every 10 seconds or when arrow keys are used to browse the rows
- `kill <PID>` <- allows for process matching specified PID to be stopped
	- `kill -SIGTERM/-15 <PID>` <- Shuts down a process and allows cleanup; should always be attempted first
	- `kill -SIGKILL/-9 <PID>` <- Immediately kills process with no cleanup; should be a last resort
	- `kill -SIGSTOP/19/23 <PID>` <- Temporarily suspends a process

- OS uses namespaces to split up available resources on the computer to processes.
	- Good for security as namespaces keep processes isolated from each other, only those in the same namespace can see each other
	- PID 0 starts when the system boots (i.e. systemd), used to provide a way of managing a user's processes, sits between the OS and the user
		- Any program or piece of software that starts, starts as a child process of systemd, meaning it's controlled by systemd but will run as its own process
- `systemctl [option] [service]` <- allows for interaction with the systemd process/daemon
	- five options are:
		- `start` <- start a process/service
		- `stop` <- stop a sprocess/service
		- `enable` <- allow a process/service to start automatically at system boot
		- `disable` <- stop a process/service from starting automatically at system boot
		- `status` <- display current status and recent log lines of a process/service

- Processes can be run in the foreground or background, putting `&` at the end of a command moves the process to the background.
	- Using Ctrl + z on a running process/command moves it to the background
- `fg` <- brings the background process back into the foreground of the terminal

#### **Automation**
- crontab is a process that's started during boot, it deals with managing cron jobs.
	- crontab = special file with formatting that's recognised by the cron process to execute each line step-by-step. Crontabs require 6 specific values:
		- MIN - What minute to execute at
		- HOUR - What hour to execute at
		- DOM - What day of the month to execute at
		- MON - What month of the year to execute at
		- DOW - What day of the week to execute at
		- CMD - The command that will be executed
	- Wildcard (*) is supported when not wanting to provide a value for a specific field
	- `crontab -e` <- used to edit crontabs through and editor i.e. nano, VIM, etc

#### **Package Management**
- Devs submit software to an "apt" repository when they want it to be accessible to the community.
	- If approved their programs and tools will be released into the wild
- `add-apt-repository` <- used to add additional repositories to the OS on top of the OS vendor's default ones
- apt repositories are checked for updates when the system they're on is updated
- Good practice to have a separate file for every different community/3rd party repo added
- Gnu Privacy Guard (GPG) key -> used to check and guarantee the integrity of software before it's added to a Linux system. 
	- If the keys don't match what system trusts and devs used, the the software won't be downloaded
- Example of adding a new repo to the system:
	1. `wget -q0 - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -` <- Downloads the GPG key and uses apt-key to trust it
	2. `touch sublime-text.list` <- creates a file and adds the repo information
		- `deb https://download.sublimetext.com/ apt/stable/` <- use a text editor to add and save the Sublime Text 3 repo into the newly created file
	3. `apt update` <- allows apt to recognise new entry
	4. `apt install sublime-text` <- installs the software which is now trusted and added to apt

- Removing packages is effectively just reversing the process:
	- `add-apt-repository --remove ppa:PPA_Name/ppa`<- removes a personal package archive (PPA) -> third-party repo
		- Alternatively file can be deleted manually
	- once removed use: `apt remove [software-name]` <- to remove the software itself

#### **Logs**
- Located in /var/log directory
	- contain info for apps and services running on the system
	- OS can automatically manage logs in a process called "rotating"
- Can be used to monitor system health and protect it
- Service logs, such as web server logs, contain info about every single request -> allowing devs or admins to diagnose performance issues or investigate an intruder's activity