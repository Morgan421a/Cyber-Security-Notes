**Car Park**

#### **What is Defensive Security?**
- Focuses on understanding what needs to be protected and implementing security measures to prevent, detect, and mitigate the impact of potential attacks
- Core Terms:
	- **Blue Team** - Group of cyber sec defenders tasked with protecting systems and responding to threats
	- **Client Infrastructure** - The networks, servers, devices, and apps belonging to an org that need protection
	- **Risk** - The likelihood and potential impact of a threat successfully harming an org
	- **Visibility** - The ability to see and monitor activity across systems to spot potential issues
	- **Threat** - Potential danger that could harm systems or data i.e. a hacker or malware

- **Security Operation Centre (SOC)** - Monitors networks and systems to detect and investigate suspicious activity or security alerts
- **Threat Intelligence** - Researches current threats, attackers, and trends to help orgs prepare and defend against potential attacks
- **Digital Forensics & Incident Response (DFIR)** - Investigates security incidents to understand how an attack happened, and contains the threat to restore affected systems

#### **Understanding The Environment**
- Defenders need to understand what exists on a client's infrastructure and how it all fits together in order to protect it
- Defensive security questions:
	- What are you protecting? (Systems and Infrastructure) -> Client Servers, data, workstations, users
	- Can you see what you're protecting? (Visibility) -> Logs, network traffic, alerts
	- What classifies suspicious behaviour? -> Repeated logins, unusual IP addresses
	- How do you stop a threat? -> Firewall rules, IP address blocking

- Once environment is understood, defenders typically organise their work around a set of foundational security concepts:
	- **Prevention** - Putting security controls in place to stop attacks before they happen i.e. firewalls, antivirus software, and regular patching
	- **Detection** - Monitoring systems and networks to identify suspicious or malicious activity through logs, alerts, and security tools
	- **Mitigation** - Limiting damage by taking action during an incident i.e. blocking traffic, isolating affected systems, or disabling compromised accounts
	- **Analysis** - Investigating what happened, how it happened, and which systems were affected by reviewing logs and other evidence
	- **Response and Improvement** - Recovering from the incident and improving defences to reduce the risk of similar attacks in the future

- Defenders' scope - Focus on protecting what belongs to their client or organisation. 
	- Includes: Devices people use everyday, servers that host apps and data, and the networks that connect systems together
	- Before applying any defences, defenders need to understand what systems exist, their purpose, and how they fit into the overall environment 


#### **Defending an Environment**
- Defenders must understand **what** exists, consider **how** it could be abused, and **apply** protections to reduce risk
- View systems as an **interconnected chain** rather than separate parts <- attackers will try to move up a chain of systems, building to their goal
- Key Defender Principles:
	- **Threat Anticipation** - Review target systems they aim to protect and ask, "What if?" 
		- Imagine realistic paths and attacker may take to achieve their goal
	- **Attack Awareness** - Attacks tend to follow recognisable stages
		- Useful to study common attack chains and frameworks
	- **Risk Prioritisation** - Identify high-value systems and targets
		- Not every part of a system carries equal risk
	- **Continuous Adaptation** - Defence must constantly evolve as threats and attackers do, techniques change, and vulnerabilities emerge

- Example systems and defences:
	- Employee devices: 
		- Regular Software Updates
		- Antivirus to detect bad programs
	- Web Server:
		- Only allow safe traffic
		- Use secure communication
	- Mail Server:
		- Spam Filters
		- Scan attachments
	- Firewall:
		- Firewall rules that control access
		- Block known troublemakers
	- The Outside Internet:
		- Restrict inbound traffic
		- Monitor for suspicious activity