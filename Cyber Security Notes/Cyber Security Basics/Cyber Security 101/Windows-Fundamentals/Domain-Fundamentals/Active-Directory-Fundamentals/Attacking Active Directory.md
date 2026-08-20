**Car Park**

### **Setup**
##### **Installing Impacket on Kali Linux**
1. Clone the GitHub repo:
	- `git clone https://github.com/fortra/impacket.git /opt/impacket` <- Copies the source code from the repo and stores it in a new directory called `impacket` within the `opt` directory
	- After cloning, several install related files will appear, including `requirements.txt` and `setup.py`
		- `setup.py` actually installs **impacket** onto the system so it can be used without needing to worry about dependencies
2. `pip3 install -r /opt/impacket/requirements.txt` <- Installs the Python requirements for **impacket**
3. `cd /opt/impacket/ && python3 ./setup.py install` <- Moves to the `impacket` directory within opt and executes the `setup.py` script using the`python3` interpreter to install the package

##### **Installing Bloodhound and Neo4j On Kali Linux**
1. `apt update && apt upgrade` <- Ensures installed packages are up to date (optional if done already prior to installing anything)
2. `apt install bloodhound neo4j` <- installs `Bloodhound` and `Neo4j`

### **Enumeration**
- Basic **enumeration** starts with an **`nmap` scan**
- **`Nmap`** = Utility designed to detect **open ports**, **running services**, and **the running OS** on a device
	- Not all services may be detected correctly and not be enumerated to it's fullest potential
	- `Nmap` cannot enumerate everything despite its complexity
- **Syntax**:
	- `nmap <target_IP>`
		- `-p <port_num>` <- flag can be used to specify ports to scan; separate each port with a comma
		- `-A` <- flag enables aggressive scan options, enabling 4 specific detection and tracing features at the same time, namely:
			- **OS detection** (`-O`) <- To guess the target's OS
			- **Version Detection** (`-sV`) <- Probe open ports for service and version info
			- **Script Scanning** (`-sC`)  <- To run default **Nmap Scripting Engine (NSE)** scripts
			- **Traceroute** (`--traceroute`) <- To map the path to the target

##### **Active Directory TLDs**
- Most common **invalid** TLD used for AD internal networks = `.local`
	- `.local` = **Invalid** and considered **worst practice** for several critical reasons:
		- **Certificate Issues** - Major **Certificate Authorities (CAs)** stopped using public SSL/TLS certs for invalid TLDs such as `.local`, making it difficult or impossible to use valid certs for services such as Exchange, IIS, or internal web apps
		- **mDNS Conflicts** - `.local` TLD is officially reserved by IANA for **Multicast DNS (mDNS)** per RFC 6762; using it for **unicast** DNS resolution can cause conflicts with Apple services and other devices relying on mDNS
		- **Future Validity** - Due to expansion of global DNS system to thousands of new TLDs, an invalid TLD used internally could **theoretically** become a valid, publicly registered domain, causing **resolution conflicts**
- **Recommended Alternative TLDs**:
	- **Subdomain of Public Domain** - Use a subdomain of a domain the org/user owns, such as ad.company.com or corp.company.com <- Most **robust** and **recommended** approach
	- **Reserved Test TLDs** - For labs or testing, use reserved TLDs such as `.test`, `.example`, `.invalid`, or `.localhost` <- Safe for **internal use** and do not conflict with public DNS or **CAs**

### **Enumerating Users Via Kerberos**
- **Kerberos** = A key authentication service within Active Directory
- **Kerbrute** = Tool used for **kerberos** pre-authentication brute forcing and Active Directory user enumeration
	- **Syntax**:
		- `kerbrute [command] [flags] [args]`
- Kerbrute User enumeration:
	- `kerbrute userenum -d <domain`