**Car Park**
- Similarly, in **PowerShell**, **Objects** are fundamental units that encapsulate data and functionality <- Elaborate, encapsulate here similar to OSI model?
- Traditional command shell <- like command prompt?
- PowerShell cmdlets using Pascal case vs without? <- without is easier
- Do cmdlets from online repos always require an internet connection to use even after download?
- `Remove-Item` <- Items in bin or perma-deleted?
- `Copy-Item` <- why `path` not wrapped in quotes like other commands?
- Why windows use \ for paths not /?
	- To avoid conflict with /, which was already reserved for **command-line switches** (options)
- Normal to forget cmdlets so quickly after learning them?
#### **What is PowerShell?**
- Tool designed for task automation and and config management
- Uses a CLI and a scripting language built on the .NET framework
- PowerShell is **Object-Oriented** = Can handle complex data types and interact with system components more effectively
- Initially exclusive to Windows, but has been expanded to macOS and Linux

- An **Object** in **Programming** = An item with **properties** (Characteristics) and **methods** (actions) 
	- e.g. a car object might have properties such as `Colour`, `Model` and `Fuellevel`, and methods like `Drive()`, `HonkHorn()`, and `Refuel()`
- Similarly, in **PowerShell**, **Objects** are fundamental units that encapsulate data and functionality <- easier to manage and manipulate information
	- A **Powershell Object** can contain file names, usernames or sizes as data (**properties**), and carry functions (**methods**) such as copying a file or stopping a process

- Traditional command shell's basic commands are **text-based** = data processed and **output as plain text**
- When a **cmdlet** (*command-let*) is run in **PowerShell** = returns objects that retain their properties and methods <- Allows for more **powerful** and **flexible data manipulation**, since they **don't require additional parsing of text**

#### **PowerShell Basics**
- Can be launched on Windows in various ways:
	- **Start Menu** - Type `powershell` in start menu search bar then click windows power shell
	- **Run Dialog** - Type `powershell` in the `Run` dialog box
	- **File Explorer** - Type `powershell` in the address bar of any folder and press `Enter` <- Opens PowerShell in that specific directory
	- **Task Manager** - Open Task Manager, go to `File > Run new task`, type `powershell`, and press `Enter`
	- **Command Prompt (`cmd.exe`)** - Type `powershell`, and press `Enter`
	- **Power User Tasks/WinX/Quick Link Menu** - Press `Windows Key + x` to open menu, click `powershell`

- When launched, user is represented with a `PS` (stands for `PowerShell`) in the current working directory

##### **Basic Syntax: Verb-Noun**
- PowerShell commands known as `cmdlets` (`command-lets`) <- More powerful than traditional commands and allow for more advanced data manipulation
	- **Cmdlets** follow a **`Verb-noun`** naming convention <- Easy to understand what each cmdlet does, for example:
		- `Get-Content` <- Retrieves (gets) the content of a file and displays it in the console
		- `Set-Location` <- Changes (sets) the current working directory

##### **Basic Cmdlets**
- `Get-Command` <- Lists all available cmdlets, functions, aliases, and scripts that can be executed in the current **PowerShell** session
	- For each `CommandInfo` object retrieved by the cmdlet, some properties are displayed on the console.
		- Command list can be filtered based on displayed property values, for example:
			- `Get-Command -CommandType "Function"` <- displays only the available commands of type "function"
- `Get-Help` <- Gives detailed info about cmdlets, including usage, parameters, and examples
	- e.g. `Get-Help Get-Date` <- Shows info regarding the `Get-Date` cmdlet
	- `Get-Help` also lists other ways to get useful info by appending some options to the basic syntax such as `-example` (`Get-Help Get-Date -example`) which shows a list of common ways in which the chosen cmdlet can be used.

- PowerShell includes **aliases** = Shortcuts/Alt names for cmdlets <- Easier for those with experience using other command-line tools to transition to PowerShell.
	- `Get-Alias` <- Lists all aliases available, for example:
		- `dir` = an alias for `Get-ChildItem`
		- `cd` = an alias for `Set-Location`

- PowerShell **functionality** can be **extended** by **downloading** additional cmdlets from **online repos**
- `Find-Module` <- Used to search for **modules** (collections of cmdlets) in online repos such as **PowerShell Gallery**
	- If exact module name = unknown, can be searched for via a similar name by filtering the `Name` **Property** and appending a **wildcard** (*) to the module's partial name using the following syntax:
		- `Cmdlet -Property "Pattern*"`
		- Search example: `Find-Module -Name "PowerShell*"` <- Finds all modules whose names contain the word `PowerShell` followed by any other characters
- `Install-Module` <- Used to download and install the desired module from the repo, making new cmdlets contained in the module available for use
	- e.g. `Install-Module -Name "PowerShellGet"` <- Downloads and Installs the `PowerShellGet` module allowing its contained cmdlets to be used


#### **Navigating the File System and Working With Files**
- `Get-ChildItem` <- lists files and directories in a location, specified with the `-Path` parameter -> Similar to `dir`/`cd`
	- No `Path` specified = displays contents of current working directory
- `Set-Location` <- Changes current directory, navigating to specified `Path` -> like `cd`
	- e.g. `Srt-Location -Path ".\Documents"`
- `New-Item` <- Creates an item <- Path and type of item need to be specified (i.e. a file or directory)
	- e.g. `New-Item -Path ".\Documents\MyNewDirectory" -ItemType "Directory"` <- Creates a Directory called `MyNewDirectory` in the documents directory
	- `New-Item -Path ".\Documents\MyNewDirectory\MyNewFile.txt -ItemType "File"` <- Creates a new text file called `MyNewFile` within `MyNewDirectory`
- `Remove-Item` <- Removes both directories and files
	- e.g. `Remove-Item -Path ".\Documents\MyNewDirectory"` <- Removes the directory`MyNewDirectory` from the specified location, in this case, the `Documents` directory
	- `Remove-Item -Path ".\Documents\MyNewDirectory\MyNewFile.txt"` <- Removes the `MyNewFile.txt` file from the specified location, in this case, the `MyNewDirectory` directory within `Documents`
- `Copy-Item` <- Copies files and directories to a specified `Destination` 
	- **Syntax:**
		- `Copy-Item -Path \file\dir\path -Destination \destination\fil\dir\name`
			- e.g. `Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt` <- Copies the `captain-hat.txt` file from the `captain-cabin` directory to the `captain-hat2.txt` file in the `captain-cabin` directory
- `Move-Item` <- Moves files and directories to the specified `Destination`
	- **Syntax:** 
		- `Move-Item -Path \file\dir\path -Destination \desired\destination`
- `Get-Content` <- Reads and displays contents of a file -> similar to `type` (`cmd.exe`) and `cat` (Unix-like systems)

#### **Piping, Filtering, and Sorting Data**
- **Piping** = Technique use in CL-enviros <- Allows the output of one command to be used as input for another.
	- Creates a sequence of operations where data flows from one command to the next
	- Represented by the `|` Symbol
	- Used across most shells (Both Windows and Unix-based)
- In **PowerShell**, **Piping** passes **objects** instead of just text <- objects carry the data **as well as** the **properties** and **methods** that describe and interact with the data
- An example of piping in PowerShell:
	- `Get-ChildItem | Sort-Object Length` <- Lists the files and directories in the current working directory and sorts them by size
		- `Get-ChildItem` - retrieves the files (as **objects**), and the **pipe** (`|`) sends those **file objects** to `Sort-Object`, which then sorts them by their `Length` (size) property.
			- **Object-Based approach** allows for more **detailed** and **flexible** command sequences

- PowerShell provides a set of cmdlets that, when combined with **piping**, allow for advanced **data manipulation** and **analysis**
- `Where-Object` <- Allows for the filtering of objects based on specified conditions
	- **Syntax**:
		- `cmdlet | Where-Object -Property "Property" -eq "Pattern"`
			- `-eq` = `equal to` -> case sensitive
			- `-ne` = `not equal to` -> case sensitive
		- e.g. `Get-ChildItem -Property "Extension" -eq ".txt"` <- Lists only `.txt` files in a directory
			- Here, `Where-Object` filters files by their `Extension` Property ensuring only files with the extension equal (`-eq`) to `.txt` are listed
		- `-eq` Operator = part of a set of **comparison operators** that are shared with other scripting languages (e.g. Bash, Python). 
			- Some of the Most useful operators from that list are:
				- `-eq` <- "**equal**" - used to **include** objects in the results based on the **specified criteria**
				- `-ne` <- "**not equal"** - used to **exclude** objects from the results based on the **specified criteria**
				- `-gt` <- "**greater than**" - filter only objects which **strictly exceed** a **specified value** <- **strict comparison** = objects **equal** to **specified value** will be **excluded** as well
				- `-ge` <- "**greater than or equal to**" - non-strict version of `-gt`, includes objects that **exceed** or are **equal to** a **specified value**
				- `-lt` <- "**less than**" - only include objects **strictly below** a specified value <- **strict comparison**, like `-gt`
				- `-le` <- **less than or equal to** - non-strict version of `-lt`, includes objects that are **below** or **equal to** a **specified value**
		- `-like` <- similar to `-eq` but is **case insensitive**

- `Select-Object` <- Selects specific properties from objects or limits number of objects returned
	- Useful for refining the output to show only the necessary details
	- **Syntax**:
		- `cmdlet | Select-Object Properties,can,be,more,than,one`
		- e.g. `Get-ChildItem | Select-Object Name,Length` <- displays only the `Name` and `Length` properties of the objects (files and directories) in the current working directory
- `Sort-Object` <- Sorts Objects based on specified property values
	- **Syntax**: 
		- `cmdlet | Sort-Object parameter`
			- The `parameter` can vary and be chained, there are many parameters available to sort by:
				- Another `parameter` is  `-Descending` which sorts objects in reverse-order
				- `-Property` Can sort by multiple object properties as such `Property1, Property2` -> sorts objects by the first property, then the second property for any ties
				- e.g. `Length, Name` <- Sorts by `Length` first, then by `Name` for files with the same size
			- As stated before parameters can be chained too, as such: 
				- `cmdlet | Sort-Object -Property Length -Descending` <- Sorts the objects based on their length in reverse order (in this case longest -> shortest)
		- e.g. `Get-ChildItem | Sort-Object -Property Name` <- Sorts objects in the current working directory by their `Name` property

- `Select-String` <- Searches for text patterns within files -> similar to `grep` (Unix-based systems) or `findstr` (`cmd.exe`)
	- Commonly used to find specific content within log files or documents
	- **Syntax**:
		- `Select-String -Path Path\to\file -Pattern "Pattern"`
		- e.g. `Select-String -Path ".\captain-hat.txt" -Pattern "hat"` <- Finds and displays lines containing the string `"hat"` in the `captain-hat.txt` file
		- Fully supports the use of **regular expressions (regex)**, allowing for complex pattern matching within files


#### **System and Network Information**
- PowerShell has a range of cmdlets that allow the retrieval of detailed information regarding **system config** and **network settings**
- `Get-ComputerInfo` <- Retrieves comprehensive **system information**, including OS info, hardware specs, BIOS details, and more
	- Provides a **snapshot** of the entire **system config** in a single command
	- Unlike its traditional counterpart `systeminfo` which retrieves only small set of the same details
- `Get-LocalUser` <- Lists all local user accounts on the system
	- Default output displays, for each user, username, account status, and description
	- Essential for **managing user accounts** and understanding the **machine's security config**
- `Get-NetIPConfiguration` <- Provides detailed info about the network interfaces on the system
	- Results include IP addresses, DNS servers, and gateway connections
- `Get-NetIPAddress` <- Shows details for all IP addresses configured on the system
	- Results include both active and inactive IP addresses

#### **Real-Time System Analysis**
- `Get-Process` <- Provides detailed view of all **currently running processes**, including their **CPU** and **Memory** usage
	- Provides a **Snapshot** not a live view
	- Useful for monitoring and troubleshooting
- `Get-Service` <- Allows for the retrieval of info about the status of services on the machine, such as which ones are running, stopped, or paused
	- Used **extensively** in **troubleshooting** by **sys-admins**, as well as **forensics analysts** hunting for Anomalous services installed on the system
- `Get-NetTCPConnection` <- Displays current TCP connections
	- Gives insights into both local and remote endpoints
	- Useful during **incident response** or **malware analysis** since it can uncover **hidden backdoor** or established **connections** towards an **attacker-controlled server**
- `Get-FileHash` <- Generates file hashes
	- Useful in **incident response**, **threat hunting**, and **malware analysis** 
	- Helps **verify file integrity** and **detect potential tampering**
- The ADS attached to a file can be viewed through PowerShell as such:
	- `Get-Item -Path "\path\to\file" -Stream *`


#### **Scripting**
- **Scripting** = The process of writing and executing a series of commands contained in a text file, know as a **script**, to automate tasks that someone would generally perform manually in a shell, such as PowerShell
	- Saves time
	- Reduces chance of errors
	- Allows for the performing of tasks that are too complex or tedious to do manually
- `Invoke-Command` <- Used to execute commands on remote systems
	- Enables efficient **remote management** and, combining it with scripting, **automation of tasks** across multiple machines.
	- Can also be used to **execute payloads or commands** on target systems during an engagement by pen-testers - or attackers alike 
	- `-ScriptBlock { ... }` <- Parameter used to execute any command (or sequence of commands) on a remote computer
		- e.g. `Invoke-Command -ComputerName RoyalFortune -ScriptBlock { Get-Service }` <- Executes the `Get-Service` command on the remote computer named `RoyalFortune`