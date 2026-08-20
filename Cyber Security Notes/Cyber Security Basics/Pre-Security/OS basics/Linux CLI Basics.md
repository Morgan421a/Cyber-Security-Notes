**Car Park**
- inode = Stores all metadata about a file, except from file name or full path
- Block in disk/filesystem context = Smallest fixed-size chunk a filesystem can give to a file

**Basic Commands**
- `pwd` = Print Working Directory <- Shows file path to **current** location
- `ls` <- Lists contents of current directory
	- `ls -l` <- Same as above but provides more details in order of: 
		1. 10-character string showing: file type (char 1) (-,d,l,c,b) and permissions (r,w,x,-) <- perms "-" means permission is denied, owner perms (chars 4-7), group perms (chars 5-7), others perms (chars 8-10)
		2. Number of hard links that point to the file's inode (stores metadata about files/directories)
		3. Owner name - username of user who owns the file
		4. Group name - name of group associated with file, users in group inherit group permissions defined in first column
		5. File size in bytes <- typically size of dir shown as its Metadata (often 4096 bytes), not the total size of its contents, *this column in special device files might display major and minor device number instead of size*
		6. Last modification time - Spans three columns showing month, day, and time (or year) <- If modified in current year, shows HH:MM, if modified in a previous year, shows the year instead of the time
		7. File Name - Name of the file or directory <- if file is a symbolic link (l), name followed by -> and the target path it points to
	- `ls <dir_name>` <- list contents of specified directory if not current

	- `ls -al` <- Displays all files including hidden files in a directory (hidden files start with a dot (.) )

- `cd` = Change Directory - Moves to named directory
	- `cd ..` - goes "back" one level

- `find <starting_point> -name <filename>` - find and prints full path to file if it exists
	- Using "~" for the starting point looks from the home directory
	- Using "/" for the starting point looks from the root
	- -name = case sensitive
	- -iname = case insensitive
	- 2>/dev/null = suppress all errors (hide them from results) i.e. perms denied

- `cat <filename or path>` = Concatenate - Used to read file contents

- `whoami` - prints current username

- `uname` - Prints system info, no flag prints kernel name (i.e. Linux)
	- `uname -a` - prints all sys info in fixed order of: kernel name, nodename, kernel release, kernel version, machine hardware, processor type, hardware platform
	- `uname -s` - prints kernel name, same as no flag (i.e. Linux)
	- `uname - r` - prints kernel release (i.e. 6.8.0-51-generic)
	- `uname -m` - prints machine hardware name (i.e. x86_64, aarch64, i686)
	- `uname -n` - prints network hostname (i.e. dev-server-01)
	- `uname -o` - prints OS name (i.e. GNU/Linux) <- *GNU extension, may not be supported on BSD/macOS systems*
	- `uname -v` - prints kernel version and build details, including build date and time (i.e. #52~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Mon Jun 17 10:51:15 UTC 2)
	- `uname -p` - prints processor type (i.e. x86_64) <- *On many distributions, often returns "unknown" if architecture is the same as `-m`*

- `df` = Disk Free - reports amount of used and available disk space on **mounted filesystems**
	- `df -h` - prints in human-readable format (KB, MB, KB)
	- `df -i` - prints inode usage instead of block usage
	- `df -T` - prints filesystem type for each mount
	- `df --total` - prints total of space across all listed filesystems
	- `df -t TYPE` - prints output limited to specified filesystem type (e.g. ext4)
	- `df -x TYPE` - prints output excluding specified filesystem type from output

- `history` - Prints commands previously used by the user

- `su - <username/root>` - switches user account via the terminal, requires password if user has one set up

- `echo` - Output any text provided
	- Enclose within " " if spaces are used