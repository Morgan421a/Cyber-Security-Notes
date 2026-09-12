### Domain Name System
- Translates human-readable domain names (e.g. google.com) into computer-readable IP addresses
- DNS resolution pathway is hierarchical, following a path
- DNS is considered a **distributed database**
	- Database scattered throughout entire internet, parts contained on different servers within different networks across the world
	- 13 root server clusters <- over thousands of actual servers per root server cluster
	- Hundreds of generic top-level domains (gTLDs) - .com, .org, .net, etc.
	- Over 275 country code top-level domains (ccTLDs) - .us, .ca, .uk, etc.

### The DNS Hierarchy
- `www.sub.example.com.`
	- Hierarchy from right (top) to left (bottom):
		- DNS root = rightmost (`.`) <- typically hidden from browser address bars
		- Top level domain = `.com`
		- Second-level domain (the specific org or site) = `example`
		- Subdomain (Specificity regarding part of site, can be multiple) = `www.sub`

### DNS Lookup
- Commands used to query a DNS server:
	- `dig <website.name>` <- **Linux** and **macOS**, also installable on some Windows Versions
		- `dig <website.name> [recordtype]` <- specify record to lookup
			- `A` <- A record (IPv4)
			- `AAAA` <- AAAA record (IPv6)
			- `CNAME` <- CNAME record (canonical name)
			- `TXT` <- TXT record
			- `MX` <- MX record (Mail Exchanger)
	- `nslookup <website.name>` <- **Windows**
		- `nslookup -type=[recordtype] <website.name>` <- specify record to lookup
			- `-type=a` <- A record (IPv4)
			- `-type=aaaa` <- AAAA record (IPv6)
			- `-type=cname`  <- CNAME record (canonical name)
			- `-type=TXT` <- TXT record
			- `-type=mx` <- MX record (Mail Exchanger)

### DNS Records
- **Resource Records (RR)** = The database records of domain name services
- Over 30 record types such as: IP addresses, Certificates, Host Alias Names, etc.
- **Important and critical configurations**
	- A single mistake can stop devices hosting a domain to become unavailable
	- **Backups should be made prior to altering database records** such that they can **easily** be **rolled back** in the event an issue occurs
##### Address Records (A) / (AAAA)
- Define the IP address of a host (maps the hostname to an IP address)
	- The most popular query
- **A** Record = **IPv4** Address
	- Modify the A record to change the hostname to IP address resolution (map hostname to different IP address)
- **AAAA** Record = **IPv6** Address
- Both on the same DNS server but are different records
##### Canonical Name Records (CNAME)
- A name is an alias of another, canonical name (maps one domain name to another)
	- One physical server running multiple services
- Example:
	- The site `mail.example.com` <-  On a single server (the canonical name)
		- The alias `chat.example.com` <- `chat` is the alias, same IP address but a different application running on the web server for the domain, in this case the chat app
		- `ftp.exxample.com` <- points to the ftp app on the web server
		- `www.example.com` <- points to the primary site on the server
- A subdomain allows a single server (IP) to host multiple distinct **Applications**. The DNS gets you to the server; the subdomain name tells the server which **Application** to run
- Allows for domain IP address to be changed without having to manually change the addresses for the aliases too
##### Mail Exchanger Record (MX)
- Determines the hostname for the mail server
	- Is a **name**, **not an IP address**
- Example:
	- `IN MX mail.example.com`
		- `IN` <- Internet
		- `MX` <- Mail exchanger record
		- `mail.example.com` <- name of the mail server
##### Text Records (TXT)
- Store human-readable text information
	- e.g. useful public information
	- Originally designed for informal information
- Can be used for verification purposes
	- e.g. If a user has access to the DNS, then they must be the admin of the domain name
- Commonly used for email security
	- External email servers validate information from the DNS
##### Domain Keys Identified Mail (DKIM)
- Specialised **TXT record**
- Stores the **public key** used to **verify** the authenticity and integrity of **emails** sent from a domain
	1. Upon a mail server receiving an email from another domain, it can see it has been **digitally signed**
	2. Receiving server then refers to the sender's public DNS server to retrieve the public key and verifies the validity of the digital signature
	- Provides assurance that the email was sent from the stated domain and not altered in transit
	- Public key preceded by `p=` within the record
- Validated by mail servers, not usually seen by the end user
- Seen within the record written as `v=DKIM1` which indicates the DKIM version
##### Sender Policy Framework (SPF)
- A **TXT record**
- A list of all servers that are authorised to send emails for the domain
- Prevents mail spoofing
	- Mail servers perform a check to see if incoming mail actually came from an authorised host
- Seen within the record written as `v=spf1` which indicates the SPF version
##### Domain-based Message Authentication, Reporting, and Conformance (DMARC)
- A **TXT record**
- An extension of **SPF** and **DKIM**
- Used by receiving email servers to **prevent** unauthorised email use (**spoofing**)
- Defines policies informing receivers of emails from (or claiming to be from) a domain regarding what they should do with the emails (e.g. accept, reject, spam, quarantine, etc.)
- If a message doesn't match the SPF and DKIM within the record on a domain, the receiver must decide what to do with the email
	- Policy is written into the **sender's DMARC TXT** record
		- Receiving server looks up **sender's DMARC record**, checks the email against their rules, and then enforces the defined policy
	- Can accept all, send to spam, or reject the email
	- Compliance reports can be sent to the email administrator
