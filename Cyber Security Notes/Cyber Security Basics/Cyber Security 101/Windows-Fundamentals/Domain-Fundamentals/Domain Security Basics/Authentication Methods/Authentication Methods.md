#### **Authentication Methods**
- In Windows Domains, all credentials are stored in the Domain Controllers
	- Upon user authentication attempt to a service using domain credentials, service asks the Domain Controller to verify if they're correct
- Two **Protocols** can be used for network authentication in Windows domains:
	- **[[Kerberos Authentication]]** - Used by any recent version of Windows; **default protocol** in any recent domain
	- **[[Net-NTLM Authentication]]**- **Legacy** authentication **protocol** kept for **compatibility** purposes
- Despite **Net-NTLM** effectively being **obsolete**, most networks still have **both protocols** enabled