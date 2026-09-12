### Trusted Platform Module (TPM)
- A **specification for cryptographic functions**
	- **Hardware** designed to help with **single device encryption functions**
		- Can be built into the motherboard or installed separately
- Includes a **cryptographic processor**
	- Allows for **random number generation** and **key generation**
- Has **Persistent Memory**
	- Includes unique keys burned in during production
- Part of the TPM handles **Versatile Memory**
	- can store Storage keys, hardware config info, and other info in the TPM
- **Password Protected**
	- Resistant to dictionary attacks
- Contains a **Unique Secret Key**
	- Not available outside of the device <- Unique to each system
	- **Encryption key linked to a computer**
		- **Can't move** an **encrypted drive** **to another computer** <- Data on the drive remains encrypted on a different computer
		- The key is on the computer
	- Used as a **physical point of reference** <- Hardware such as a drive can be associated with the TPM
		- Referred to as **A Root of trust** (RoT) <- TPM can be used to **ensure** that the **computer** **being communicated with** **across** a **network** actually **is** the **expected device**
		- TPM can be used to **determine** **if** a **computer** has been **modified** or **tampered with**
	- Since TPM is physically apart of a system, it can't be easily copied and moved to another computer
#### TPM in BIOS
- TPM features can be enabled/disabled in the BIOS
	- Typically under **TCG** (Trusted Computing Group) in the security tab

### Hardware Security Module (HSM)
- Often used in large environments
	- Server clusters, orgs with many diverse devices
- Often used to **centralise** the **backup of keys across** all **systems**
	- **Secured key storage for servers**
	- **Lightweight HSMs** for personal use, comes in many forms, such as a smart card, USB, flash memory, etc.
		- ![[Pasted image 20260906095015.png|299]]
		- Example of a Lightweight HSM
- Often **high-end cryptographic hardware** such as a **plug-in card** or **separate hardware device**
- Often accelerated cryptographic functions between devices
	- e.g. HSM handles encryption and decryption for a web server instead of it happening on the web server itself
	- Only the HSM knows the key

### TPMs and HSMs
- **TPM** (Trusted Platform Module)
	- Used on a **single system**
	- **Secure data on** a **local device**
	- Often **built into a motherboard** **or** **available as** an **add-on module**
	- Typically used for Mobile phone booting, Screen locking, and encrypted storage
- **HSM** (Hardware Security Module)
	- Used by **many systems**
	- **Secure data across multiple devices**
	- **Often** deployed as a **high-end server or appliance in** a **data centre**
	- Typically used to protect the Certificate Authority Key on a central secure device or protect important keys in an org's infrastructure