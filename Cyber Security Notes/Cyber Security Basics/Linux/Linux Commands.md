==`man <command>`== - open the manual for specified command. q to quit, / + n or N to search

e.g. `man <man>` - prints the manual for the manual

If no manual,  command might be built into the shell, use ==`help <command>`== instead.



==`ping <IP address/Website URL`== - Uses ICMP to check connection performance between devices

Same on Linux and Windows 

e.g. 
![[Pasted image 20260710111556.png]]



==`ssh <user>@<remote host name>`== - connects to specified host system using secure shell, if no user specified will default to current username

`-p <port number>` - specifies which port to connect to, 22 is the default when not specified. Changing default SSH ports can help protect against bot attacks (most scripts are written assuming port 22)

e.g. `ssh -p 2220 morganknight@bandit.labs.overthewire.org` 



==`cat <filename>`== - concatenate; 

- Reads data from a source (user input in shell or data from a file) and writes it to a destination (the shell or a chosen file)
	- e.g. display text data of file in terminal
	- With no file or if filename is - , reads [[Linux Rules|stdin]]
- combine multiple files into one output or a new file
- create files
- append data to existing file
- e.g. `cat <readme.txt>` - prints readme.txt's content in the terminal. text files are printed as readable text, binary files (like .exe, .jpg, .zip, .pdf) will print raw data bytes instead
- `cat file1.txt file2.txt > combined.txt` - combines the text from file 1 and 2 into the new combined.txt file, creates the file if one doesn't already exist
- `cat > newfile.txt` - **Overwrites existing content without asking if file already exists**
	- creates a new file if no file with same name exists
	- allows input to be added to file via terminal such as "Hello World"
	- Ctrl + D stops cat from reading input and closes the file.
	- `>` tells shell to send what `cat` would normally display to a file instead
- `cat >> existingfile.txt` - Add stuff to end of existing file without overwriting
	-  Same input method and exit as new file command
- `cat < filename` - Shell opens file = uses current user's permissions, then redirects it to cat's standard input, cat command receives no args, just reads from its input stream
	- Allows files starting with - to be read strictly as an input instead of an option (including files named only -)
- `cat filename` - the cat command itself opens specified file in the command-line argument



==`file filename `== - identifies file type

`-b` only show file type, not filename

`-i` output MIME type and charset

`-z` look inside compressed files to see what's inside without extracting (doesn't work on directories)

lists file properties from inside out compressed files

cannot see inside folders but can report the properties of the folder itself

e.g `file -b -i -z documents.zip` prints:
`text/plain; charset=us-ascii compressed-encoding=application/gzip; charset=binary
`
`text/plain` - the type of file within the compressed file

`charset=us-ascii` - the charset used within the file

`compressed encoding=application/gzip` - identifies compression method used to encode file

`charset=binary` - the charset used by the zip file itself



==`du <filename/filepath>`== - shows disk usage information of specified file

- numbers on left indicate usage in bytes
- `-h` / `--human-readable` - human readable results
- `-s` / `summarize` - summarise directory's usage for argument 
	- provided in human readable format (when written as `-sh` )
- `-a` / `--all` - list sizes of all files and directories in file path 
	- `-ah` for readability
	- Also lists hidden files - good for finding them when directory disk usage ≠ total usage of visible files
- `--max-depth=X` / `-d X` - show size of sub-directories and files where X is how many folders deep to look
	- X can be 0 (top level) to infinity (only looks as far as there are layers)
- `--time` - shows when last mod to file was made
- `-c` / `--total` - adds total usage at bottom of list
	- `-ch` for readability
- `-X` / `--exclude=Pattern` - excludes file with specified extension, where `Pattern` is the extension such as .dll

- e.g

- `du documents` => `8    documents`

- `du -h documents` => `8.0K   documents`
- `-sh` would print the same here as there are no sub directories within documents

- `du -ah documents` => 
- `4.0K	documents/document 
- `8.0K	 documents

- `du -h --time documents` =>  `8.0K	   2026-07-09 20:53	  documents`
- `-ah --time` => display last modified time of all files and sub-folders too

- `du -ch` =>  
- `8.0K 	  newcatfile folder
- `8.0K  	total`

- `du -ah --exclude="*.txt" documents` => `4.0K	  documents
- excludes the .txt files from the results therefore only showing the folder alone




==`find <filepath> -name/-iname "document.txt"`== - finds specified file if it exists within given file path or current directory (.) and its sub-directories if no path given, / can be used to search entire file system from root
- using `find . -name ".*"` - finds all files starting with . (can find hidden files whose names all start with . )
- `-name` - case sensitive name of file to find
- `-iname` - case insensitive name of file to find
- `"*filename*"` - searches for all files with the specified name or ending if using something like `"*.txt*"` will find all files ending with `.txt`
- `-type d` - find directories
- `-type f` - find files
- `-executable` - find executable files
- `-mtime -X` - files changed less than X days ago
- `-mtime +X` - files changed more than X days ago
- `-mtime X` - files changed exactly X days ago
- can use logical operators - `-and`, `-or`, `-not` to combine options  
- `()` to create precedence, **must use \ to escape as such `\(options\)' 
- `-maxdepth X` - sets how far to look within a directory where X is the number of layers; **Check du command notes**
- `-size [filesize][units (c,k,M,G,T,P)]` - looks for files of the specified size in the specified unit
- e.g. `find /home/User1/Documents -iname "document.txt"` =>
- `/home/User1/Documents/Documents/document.txt`



==`nslookup -type=[record type] subdomain.second-level-domain.topleveldomain`== - Used to make DNS queries and view the results

`nslookup ` - used alone enters interactive mode which allows for multiple queries without the need to retype the command.
	e.g. `nslookup`
	/>`set type=recordname`
	/>`google.com`
- Prints results based on the requested record, if no record type set assumes type=A

`-type=A ` - Looks up the value of the A record (IPv4 Address) of the domain name
e.g. `nslookup -type=A google.com`
Prints IPv4 Address results , some domains may have multiple A records for load balancing (rotates user requests through list of IPs to spread traffic out) and failover (If one IP is down browser tries next one automatically, helps keep site online)

`-type=AAAA ` - Looks up the value of the AAAA ("Quad A") record of (IPv6 Address) of the domain name
e.g. `nslookup -type=AAAA google.com`
Prints IPv6 Address results , multiple records possible again, see        `-type=A flag` for details

`-type=CNAME ` - Looks up value of the CNAME (Canonical Name) record of domain name

	e.g. nslookup -type=CNAME store.tryhackme.com
- prints the canonical (real) name of the domain, in this case it prints as `canonical name = shops.myshopify.com.` Some domains like google don't use canonical names and use direct A/AAAA records instead

`-type=MX ` - Looks up value of the MX (Mail Exchanger) record of the domain name

	e.g. nslookup -type=MX google.com
- Prints the mail exchanger of the domain, in this case it's `mail exchanger = 10 smtp.google.com.`

`-type=TXT ` - Looks up value of the TXT (Text) record of the domain name

	e.g nslookup -type=TXT google.com
- Prints the value of the TXT record of the domain, in this case `google.com	text = "Z29vZ2xl"` There's a lot more but this is just one line as an example

`-type=ANY ` - Looks up all the records available for the domain name (*Disabled by some servers for security)

	e.g nslookup -type=ANY google.com
- Prints all of the records available for google, too long to print here, deprecated or disabled by a lot of major DNS providers like Google, Cloudflare and a lot of ISPs for security purposes 
- Likely to only show up as  `timed out` if deprecated or blocked

`nslookup` is now deprecated and viewed as outdated, `dig` is it's recommended replacement 

==`dig subdomain.second-level-domain.topleveldomain [record type] [flags]`== - more modern version of nslookup but doesn't come with an interactive mode, output is verbose by default

`+short` - simplifies the verbose output 

`A` - Prints IPv4 Address record for domain name

	e.g dig google.com A | dig google.com
- Prints the IPv4 address record *See `nslookup -type=A` flag regarding domains with multiple IP's listed*

`AAAA` - Prints IPv6 Address record for domain name

	e.g dig google.com AAAA
- Prints the IPv6 address record *See `nslookup -type=A` flag regarding domains with multiple IP's listed*

`MX` - Prints Mail exchanger record for domain name

	e.g dig google.com MX

`CNAME` - Prints Canonical (real) name for domain name

	e.g dig google.com CNAME
- Some domains like google don't use canonical names and use direct A/AAAA records instead

`TXT` - Prints value of TXT record for domain name

`+noall +answer` - Hides stats/headers and shows answer section only (includes TTL). Good for investigations over `+short`

	e.g dig google.com MX +noall +answer


