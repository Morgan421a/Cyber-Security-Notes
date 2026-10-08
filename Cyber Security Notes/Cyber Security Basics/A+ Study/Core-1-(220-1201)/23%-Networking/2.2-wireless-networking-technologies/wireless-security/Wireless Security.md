- Encryption and access control is vital to ensuring unauthorised individuals can't access private wireless networks
- Different Wi-Fi Security protocols exist with differing levels of security, namely:

#### WEP (Wired Equivalent Privacy):
- Introduced in 1990s with og 802.11 standard
- **Encryption** -> **40-bit or 128-bit** **pre-shared key** (PSK)
- **Initialisation Vector** (IV) -> **24-bit** transmitted in **clear text**
- **Weaknesses**:
	- Vulnerable to attacks using tools such as Aircrack-ng
	- Can be cracked easily
	- **Not suitable for modern networks**
- **Lacks scalability in larger networks**

#### WPA (Wi-Fi Protected Access):
- Introduced as a replacement for WEP
- **Encryption** ->**RC4 algorithm** with **Temporal Key Integrity Protocol** (TKIP)
- **Initialisation Vector** (IV) -> **48-bit** transmitted in **clear text** <- Message Integrity Check (MIC) protects frame contents from modification
- **Key Features**:
	- Message Integrity Check (MIC) prevents data tampering
	- Support pre-shared key (PSK) and enterprise authentication mode
- **Weaknesses**:
	- Vulnerable by modern standards
	- TKIP has known vulnerabilities
- **Avoid using WPA unless absolutely necessary**

#### WPA2 (Wi-Fi Protected Access 2):
- Introduced in IEEE 802.11i standard
- **Encryption** -> **Advanced Encryption Standard (AES)** with **128-bit or 256-bit key**
- **Integrity** -> Counter Mode with Cipher Block Chaining Message Authentication Code Protocol (**CCMP**)
- **Key Features**:
	- Strong confidentiality and data integrity
	- Available in personal (PSK) and enterprise mode
- **Weaknesses**:
	- Open to brute-force dictionary attacks if weak passwords used
- **Still widely used but requires strong, complex passwords**

#### WPA3 (Wi-Fi Protected Access 3):
- Introduced as the newest standard to address WPA2 vulnerabilities
- **Encryption** -> **AES** **with** **Simultaneous Authentication of Equals** (SAE) **handshake**
- **Key Features**:
	- Resistant to offline brute-force attacks
	- Has forward secrecy to protect past communications
	- Protected Management Frames (PMF) to prevent session hijacking
- **WPA3-Enterprise** <- Uses **192-bit cryptographic keys** for high-security environments
- **Challenges**:
	- Device compatibility issues leading to gradual adoption
	- Typically used in hybrid mode with WPA2
- **Preferred for new deployments, though background compatibility may be required**

### Additional Security Measures
- **MAC Address Filtering**:
	- Allows or denies access based on a device's MAC address
	- Can be bypassed easily using MAC address spoofing
	- Best used as a supplementary security measure as opposed to a standalone solution
- **Disabling SSID (Service Set Identifier) Broadcast**:
	- Hides network name from casual users
	- Special tools can still be used to detect hidden networks
	- Best used as part of a layered security approach

