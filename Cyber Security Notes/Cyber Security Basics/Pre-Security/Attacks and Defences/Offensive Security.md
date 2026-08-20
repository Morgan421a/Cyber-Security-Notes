**Car Park**

#### **What is Offensive Security?**
- Focuses on testing systems by attempting to break them, aiming to identify weaknesses before real attackers can exploit them
- Starts with questions:
	- What is exposed?
	- What can be accessed?
	- What assumptions does the system make?
- **Penetration testing (AKA Ethical Hacking)** - A form of offensive security:
	- An ethical, legal and structured method for identifying weaknesses so they can be addressed
- **Vulnerability Researcher** - Identify and validate undiscovered weaknesses in software and hardware
- **Red Team Operator** - Simulate real-world adversaries to test an orgs detection, response, and defensive capabilities

- Core Offensive Security Terms:
	- **Red Teaming** - Structured, authorised attack methodology which simulates a real adversary to test the effectiveness of defences and find vulnerabilities within a defined scope
	- **Penetration Test** - Structured security assessment where an authorised tester attempts to identify and exploit vulnerabilities within a defined scope to understand real-wold risk 
	- **Vulnerability** - A weakness or flaw in a system, application, or configuration that an attacker could abuse
	- **Exploit** - A technique or method used to take advantage of a vulnerability to achieve a specific outcome i.e. accessing restricted functionality or data
	- **Scope** - The boundaries of what is allowed to be tested during an engagement. Scope defines which systems, applications and actions are permitted and what is off limits
	- **Enumeration** - Collecting details about a system, users, and services to find weak points

#### **Finding Weaknesses**
- `gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt`
	
	- `gobuster` - Command line tool used to discover web content on a website
	- `dir` - Specifies directory and file enumeration mode <- attempts to find hidden directories and files on a web server
	- `--url http://www.onlineshop.thm/` - Sets the target website for gobuster to scan
	- `-w /usr/share/wordlists/dirbuster/directory-list.txt` - Specifies the wordlist that gobuster will use to guess directory and file names 


#### **Exploiting Weaknesses**
- Weaknesses can be chained together to go from minor consequences to serious consequences
- Key ethical hacking points to memorise:
	- **Ask questions** - Don't assume a feature works as intended, ask "What if it doesn't?"
	- **Test the unexpected** - Try actions and inputs the devs didn't consider 
	- **Chain small weaknesses** - Tiny flaw(s) may be harmless alone, but could be connected to create a bigger impact
	- **Think like an adversary** - "How would a mal-actor approach this target?"

- Attackers are usually focused on gaining valid credentials (i.e. username and password) to gain access to private areas or features of an application, once they've gained entry they have access to:
	- **Sensitive functionality** - Features that perform essential actions i.e. modifying data, viewing restricted content, or triggering processes that should only be available to authorised users
	- **User data** - Personal private info belonging to users which attackers may steal, abuse or sell i.e. names, email addresses, or account details
	- **Administrative features** - High-privilege functionality which allows attackers to manage users, change settings, or gain full control of the app if accessed
	- **Further attack opportunities** - Access may expose other vulnerabilities, allowing attackers to expand their access or move deeper into the app

- **Hydra** - Password-testing tool that automates login attempts against a target app using a wordlist
	- Systematically tries each password in the wordlist to see if login is successful. <- Called a **Dictionary Attack** as it relies on a predefined list of possible passwords
	- `hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V`
		
		- `hydra` - Command line tool used to perform the dictionary attack
		- `-l admin` -  Attempts to login using the username `admin`
		- `-P passlist.txt` - Specifies the password list to try
		- `www.onlineshop.thm` - Sets the target website
		- `http-post-form` - Indicates that it's an HTTP POST request form
		- `"/login:username=^USER^&password=^PASS^:F=incorrect"` - Specifies how the login request is sent and how Hydra determines whether a login attempt has failed
		- `-V` - Enables verbose output <- Displays each username and password attempted