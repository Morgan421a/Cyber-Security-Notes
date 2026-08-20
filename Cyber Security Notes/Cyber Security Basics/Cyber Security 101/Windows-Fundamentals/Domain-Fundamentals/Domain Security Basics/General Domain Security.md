- Malware can spread from domain devices to the Active Directory, compromising the configuration within the AD to establish persistence and control
	- Malware residing on a compromised AD is extremely dangerous as every device on a domain trusts its AD, meaning the malware on the AD can automatically push itself to every connected device
	- General Cycle example:
		1. **Entry:** Malware enters via a single user (e.g. phishing)
		2. **Escalation:** Malware steals credentials to become a Domain Admin
		3. **Infection of AD:** Malware Writes malicious code into a **GPO** or the **`SYSVOL`** folder
		4. **Propagation:** AD automatically pushes the code to **all devices** on the network