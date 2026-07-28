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