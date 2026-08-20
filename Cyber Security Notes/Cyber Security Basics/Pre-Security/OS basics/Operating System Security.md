**Car Park**

**OS Security Introduction**
- Three main points to protect:
	- Confidentiality - Ensuring private and secret files are only available to the intended persons
	- Integrity - Ensuring no one can tamper with files stored on a system while being transferred on the network
	- Availability - Ensure the system is available to its user when they want to use it

**Common Examples of OS Security**
- Three weaknesses targeted by malicious users:
	- Authentication and weak passwords
	- Weak file permissions
	- Malicious programs

- Authentication and Weak Passwords:
	- **Authentication** - The act of verifying someone's identity, three main ways to do so are:
		- Something they **know**, like a password or PIN code
		- Something they **are**, such as a fingerprint
		- Something they **have**, such as a phone number through which an SMS message can be received
	- Passwords are the most commonly used form and thus are the most targeted. A lot of users have weak passwords or use the same password across multiple logins/accounts which attackers are aware of. 
		- Personal info is also often used such as DoB or pet names which are easy to remember and assumed to be unknown to attackers, but attackers are also aware of this tendency among users
	- If an attacker can guess a password to a user's account they'll be able to access their private data, as such complex passwords must be used and should vary between different accounts

- Weak File Permissions:
	- Proper security dictates the **principle of least privilege** - Files should only be accessible to those who need to access it whether in a work environment or in a personal setting <- **Essentially "who can access what?"**
	- Weak file permissions allow **easy access to files** for attackers, enabling them to attack both **confidentiality** and **integrity**
		- Confidentiality - Able to access files they shouldn't be able to
		- Integrity - May potentially modify files they shouldn't be able to edit

- Access to Malicious Programs:
	- Targets of an attack (confidentiality, integrity, availability) depend on the type of the malicious program
		- Availability - one example that attacks this is **ransomware**, which encrypts the user's files making them unreadable without knowing the encryption password. Attackers offer the user the encryption password if the user is willing to pay a "ransom"

- Credential discovery workflows
	- Sequence: SSH → file enumeration → credential extraction → account switching → privilege escalation. Pattern is reusable across similar systems.

- Password-protected `su` transitions
	- Use SSH config for Host aliases to simplify repeated account switches and reduce typing errors during multi-step escalation chains.
		- SSH host alias = Nickname for a computer instead of needing to type its address, username and port number each time i.e. ssh work, instead of, ssh user@192.168.1.55 -p 2222
			- Can be created in the *~/.ssh/config* file or defined in *~/.bashsrc* or *~/.bash_aliases* for simpler, one-off connections


## **Summary**
- Three main pillars of security (CIA Triad):
	- Confidentiality - A user's data cannot be viewed or accessed by unauthorised persons
	- Integrity - A user's data has not/cannot be modified by unauthorised persons
	- Avaliability - A user can access their devices and data at anytime they wish

- Examples of OS Security:
	- Authentication and Passwords
		- Protect User accounts through a verification process, usually requiring 1 of 3 methods to verify identity:
			- Something they know: i.e. password or PIN
			- Something they are i.e. Biometrics (Fingerprint)
			- Something they Have i.e. Phone with SMS capabilities
		- Breach typically = Confidentiality violation which can lead to both Avaliability (i.e. changing user's password) and Integrity (i.e. modifying user data) violations
	- Malicious Programs
		- The use of programs such as ransomware to gain unauthorised access to user accounts or data. i.e. Ransomware to encrypt a user's data and offer the password to unencrypt it if they user pays a "ransom"
		- Breach typically = Avaliability violation and technically an integrity violation and the encryption is a data modification in regards to ransomware
		- Violated CIA pillar and attack target dependent on type of malicious program/what it does to the system or the user's data
	- Weak File Permissions
		- Not following the Principle of least privilege leading to someone being able to access data and/or modify data/files they shouldn't be able to
		- Breach typically = Confidentiality and Integrity violation which, depending on what is stored on a user's files, could also become an Avaliability violation i.e. finding a stored password and then logging into and changing the password of that user's account

- A violation of one CIA pillar can always turn into a violation of multiple or all three so it is beyond important that all are sufficiently protected.

- Credential Discovery Workflows:
	- SSH into machine 
	- Find passwords mistyped in terminal history (using `history` command) or user files 
	- Use passwords to log into different accounts (Use `su <username>` for quick switching)
	- Escalate permissions by logging in to accounts with higher permissions 
	- Log into root/administrator account for complete dominion over the system

- Use SSH Config aliases to simplify switching connections by using a nickname as opposed to the full device IP and port every time
	- Reduces Typing errors during multi-step escalation processes