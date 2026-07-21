
**What is DNS?**
- DNS is a way to communicate with devices on the internet without having to remember their IP address. i.e. instead of 104.26.10.229, can remember tryhackme.com instead

**Domain Hierarchy**
- Top Level Domain ([[TLD]])
	- Most right hand part of domain name, i.e .com, .edu, .co.uk etc
	- Two types of TLD:
		1. gTLD
		2. ccTLD
	- Over 2000 TLDs exist

- Second-Level Domain
	- Limited to 63 characters +  TLD
	- Can only use a-z, 0-9 and hyphens (-) (Cannot start with, end with or have consecutive hyphens)
	- e.g. Google in Google.com is the second level domain

- Subdomain
	- Sits to the left of Second-Level Domain using a full-stop (.) to separate them. i.e admin is the subdomain in admin.tryhackme.com or www.
	- Same creation restrictions as Second-Level Domain
	- Multiple subdomains can be used if split with periods to create longer names i.e. jupiter.servers.tryhackme.com
	- Length must be kept to 253 chars or less
	- No limit to number of subdomains in domain name

**DNS Record Types**
- DNS isn't just for websites, multiple types of DNS records exist
- Some common DNS records are:
	- A record - Resolve to IPv4 addresses
	- AAAA record - Resolve to IPv6 addresses
	- CNAME (Canonical NAME) record - Resolve to another domain name e.g. store.tryhackme.com returns a CNAME record shops.shopify.com, then another DNS request is made to shops.shopify.com to get the IP address
	- MX (Mail Exchanger) record - Resolve to address of servers that handle the email for the domain being queried, i.e. MX record response for tryhackme.com looks for something like alt1.aspmx.l.google.com.
		- Comes with a priority flag which tells client what order to try the servers in, good for if main server goes down and email needs to be sent to a backup server
			- Priority flag is represented by a numerical priority value (preference) lower number = higher priority
	- TXT (TeXT) record - Free text fields to store any text-based data.
		- Some example uses are: listing servers with the authority to send an email on behalf of the domain (good to fight against spam and spoofed email), verify ownership of domain name when signing up for third party services.

**Making a DNS Request**
1. Upon requesting a domain name computer first checks local cache to see if it's been looked up previously, if not a request is sent to your recursive DNS server
2. Recursive DNS server checks own local cache for recently looked up domain names, if result found locally responds to computer with that domain name (common for popular domain names like google, Facebook, twitter).
	- If request can't be found locally recursive server sends request to the Root DNS Server
3. Root DNS Server takes the request and sends a referral to the correct TLD Server based on the recursive DNS server's request.  The Recursive DNS Server then iteratively queries the TLD server (e.g., for `www.tryhackme.com`, it refers the request to the `.com` TLD servers).
4. TLD server uses its records to find the correct authoritative server to answer the DNS request.
5. Depending on record type for domain name, Authoritative DNS Server sends the DNS record back to the Recursive DNS Server where a local copy is cached for future requests and then relays it back to the OG client that made the request.
	- DNS records have a TTL value represented in seconds 
	- Caching makes future requests faster by removing the need to make a DNS request every time a user communicates with a server
	- domains use nameservers listed in the authoritative DNS server to function. Often have multiple as backups in case one goes down
		- Shared Authoritative DNS (Most common) - provided by domain registrars, web hosting provider or managed DNS services. 
			- Usually used by small to medium websites
		- Custom/Private Authoritative DNS (Rare)
			- Typically only used by very large orgs (like google or major banks) or specialised technical entities.
			- Use their own physical Authoritative DNS Servers
			- Allows for absolute control, specific security configs or high query volumes
			- Requires maintaining servers in multiple geographic locations and ensuring they're always online = expensive and complex


## **Summary**

- Domain Name System (DNS) = A way for developers to give websites a human-readable name such that users of websites don't need to memorise the IP address for every website they use
- Domain Hierarchy = The way in which a domain name is formed/written from its parts
	- Top level domain (TLD) - Sits furthest right on the name, historically used to inform visitors of the website's purpose, i.e. .com, .edu, .gov
		- Two types of TLD include, Generic Top Level Domain (Gtld) and Country Code Top Level Domain (ccTLD)
	- Second Level Domain (SLD) - Sits directly left of the TLD i.e. Google in Google.com. 
		- Can be up to 63 characters long + TLD
		- Hyphens (-) can be used but must not be at the start or end of the name and cannot be consecutive
	- Subdomain - Sits directly left of the SLD and are separated by dots (.)
		- Can have as many subdomains as will fit in the Domain Name character limit as long as they're separated by (.)
- Domain name character limit = **253 Characters** <- max length of whole domain name (sum of all parts)

- Record Types = The records used to store specific information for a Domain, some include:
	- A Record - Resolves to the IPv4 address of the website
	- AAAA Record - Resolves to the IPv6 address of the website
	- CNAME - Canonical (real) Name, resolves to the name of the website upon which the named website is hosted on
	- MX (Mail Exchanger) Record - Resolves to the addresses to and from which emails can be sent
		- Uses a hierarchy in the event that one stops working and moves to the next based on a pre-set priority list whereby the lowest number = highest priority
			- Helps prevent complete halt in communication
	- TXT (Text) Record - Stores plain text for the website
		- i.e. a list of servers with the authority to send emails on behalf of the domain,  User login credentials used for verification <- Had to check notes

- DNS Request Process:
	1. User requests a website
	2. Computer checks local cache to see if it has the website's address saved 
		- If yes request data and information straight from corresponding server
	3. If no, forward request to user's recursive DNS server who will then check their own local cache for the address first
	4. If still no forwards the request to the Root DNS Server who will then locate and forward a list of IP addresses (referral) to the recursive DNS server <- Had to check notes
	5. Recursive DNS server uses iterates through received address list and sends the request to each TLD server until the one corresponding to the requested site's TLD is found. <- Had to check notes
	6. TLD server uses its records to find the authoritative DNS server to respond to the DNS request <- Had to check notes
	7. Depending on record type for the Domain Name, authoritative DNS server sends response back to the recursive DNS server whom will store the response on their local cache for the sake of faster server location in the future <- Had to check notes
	8. Recursive server sends response back to the user's computer and the page is loaded
		- DNS records have a Time to live (TTL) value represented in seconds dictating when they will expire from the cache

- Different types of authoritative DNS servers exist and can be used depending on a client's needs: <- Had to check notes
	- Shared authoritative DNS - The most common, provided by domain registrars, web hosting providers or managed DNS services <- Had to check notes
		- Typically used for small to medium websites <- Had to check notes
	- Custom/Private authoritative DNS - Quite rare, Organisation's own authoritative servers <- Had to check notes
		- Usually only used by big organisations or specialised technical entities <- Had to check notes
		- Uses own physical authoritative DNS servers <- Had to check notes
		- Grants absolute control, specific security configs or high query volumes <- Had to check notes
		- Expensive and complex due to need to maintain many servers in different geographic locations and ensuring they're always online <- Had to check notes