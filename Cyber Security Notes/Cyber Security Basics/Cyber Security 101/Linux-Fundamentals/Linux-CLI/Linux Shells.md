
### Interacting with a shell
- Most Linux distros use **Bash** (Bourne Again Shell) as their default shell; default shell displayed upon opening terminal depends on Linux distro
- `grep` <- Search for specified word or pattern within a file
	- **Syntax**: 
		- `grep pattern filename`
		- e.g. `grep THM dictionary.txt` <- searches the `dictionary.txt` file for all lines which match the pattern/word `THM`

### **Types of Linux Shells**
- Multiple shells are installed in different Linux distros
- Each shell has its own features and characteristics
- `echo $SHELL` <- Displays which shell is currently being used
- The `/etc/shells` file contains all the installed shells on a Linux system
	- `cat /etc/shells` <- lists all available shells on the current Linux OS
- Shell can be changed by typing the name of the shell tat is present on the OS
	- e.g. `zsh` <- Switches to the `zsh` shell
- `chsh -s /usr/bin/shellname` <- permanently changes the default shell for the terminal
- Many types of Linux shells exist, some of them are:

##### **Bourne Again Shell (Bash)**
- Default shell for most linux distros
- Replaced shells such as `sh`, `ksh`, and `csh`, each of which had different capabilities some of which bash borrowed from to become an enhanced version of them
- Some of Bash's key features are:
	- Widely used with shell scripting capabilities
	- Offers tab completion (pressing `tab` key can autocomplete command based on a possible match or give a list of suggestions for completing it)
	- Bash keeps a history file and logs of all of a user's commands; `up` and `down` arrow keys can be used to use the previous commands without needing to retype them
		- `history` <- can be typed to display all of a user's previous commands

##### **Friendly Interactive Shell (Fish)**
- Not default in most Linux distros
- Greater focus on user-friendliness than other shells
- Some key features of Fish are:
	- Very simple syntax, easier for beginner users
	- Auto spell correction for typed commands, unlike bash
	- Command prompt can be customised using Fish
	- Syntax highlighting; colours different parts of a command based on their roles, improves readability of commands and helps spot errors
	- Provides scripting, tab completion, and command history

##### **Z Shell (Zsh)**
- Not installed by default in most Linux distros
- Considered a modern shell which combines the functionalities of some previous shells
- Some key features of Zsh are:
	- Zsh provides advanced tab completion and is capable of writing scripts
	- Provides auto spell correction for commands
	- Offers extensive customisation that may make it slower than other shells
	- Provides tab completion, command history functionality, and several other features

### **Shell Scripting and Components**
- **Shell script** = A set of commands
	- Can remove the need for manually entering repetitive commands for a task by combining them into a script and just executing it instead
	- Scripting can be done using a shell as well as various programming languages
	- `.sh` = The default extension for bash scripts
	- Scripts should start with a **shebang (`#!`)** followed by the name of the interpreter to use while executing the script
		- e.g. `#!/bin/bash` <- defines bash as the interpreter
- `chmod +x script_name` <- Used to grant a script execution permissions

##### **Variables**
- A **Variable** stores a value inside it
	- e.g. `read name` <- `read` takes an input from a user, `name` is the variable used to store the input
		- `$name` <- used to reference/expand the value of a variable in Bash
- Can be defined in various ways, one being shown prior for example
	- Can also be defined as `varname=value`
- example script:
	````shell
		#!/bin/bash
		echo "Hey, What's your name?"
		read name
		echo "Welcome, $name"
	````
	- Script displays the first message, then waits for user input and stores the value in the `name` variable. Finally, script displays the message "Welcome, " with the value stored in the `name` variable called used `$name`

##### **Loops**
- Example Syntax
	````shell
		#!/bin/bash
		for i in {1..10};
		do
		echo $i
		done
	````
	- Variable `i` iterates from 1 to 10 and executes the code below each time
	- `do` indicates start of the loop code
	- `done` indicates end of the loop code
	- Code written between `do` and `done` is what will be executed during the loop
	- `echo $i` displays the variable `i`'s value every iteration

##### **Conditional Statements**
- Executes a piece of code only when a condition is satisfied, otherwise will execute another piece of code
- Example syntax:
````shell
	#!/bin/bash
	echo "Please enter your name first:"
	read name
	if [ "$name" = "Stewart" ]; then
	        echo "Welcome Stewart! Here is the secret: THM_Script"
	else
	        echo "Sorry! You are not authorized to access the secret."
	fi
````
- `read name` takes a user's input and stores it in the `name` variable
- `if [ "$name" = "Stewart" ]; then` starts the conditional statement and compares the value stored in the `name` variable with the string `"Stewart"`
	- If value of `name` matches string `"Stewart"`, displays the secret to the user
	- if value of `name` doesn't match string `"Stewart"`, displays the message under the else statement
- `fi` used to end the condition

##### **Comments**
- Sentence added to code to help with understanding different parts whether for writer's future reference or another user's
- In Bash `#` is used to start writing a comment 
	- `#` only for single line comments
	- No true native multi-line comment in Bash
- Example Syntax
````shell
	#!/bin/bash

	# Asking The user to enter a value
	echo "Please enter your name first:"
	
	# Storing the user input in a variable 
	read name
	
	# Checking if the name the user entered is equal to required name
	if [ "$name" = "Morgan" ]; then
	
	# If input equals required name, display the following line
	     echo "Welcome Morgan! Here is the secret: THM_Script"
	
	# Defining sentence to be displayed if condition fails
	else
	
	    echo "Sorry! You are not authorised to access the secret."

	# Ending the condition
	fi
````


