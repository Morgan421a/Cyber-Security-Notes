### **BitLocker**
- **BitLocker Drive Encryption** = Data protection feature that integrates with the OS 
	- Deals with the threats of data theft or exposure from lost, stolen, or inappropriately disposed computers

- Provides the most protection when used with a TPM version 1.2 or later.
	- TPM works with BitLocker to ensure device hasn't been tampered with while offline
- BitLocker can **lock** the normal **startup process** until the user supplies a **PIN** or inserts a removable device that contains a **startup key**
	- Provides MFA and assurance that a device can't start or resume from hibernation until the correct **PIN** or **startup key** is presented

- Devices without a TPM can still use BitLocker to encrypt the OS drive, however it requires a user to either:
	- Use a **startup key** <- A file stored on a **removable drive** that is used to start the device or when resuming from hibernation 
	- Use a **Password** <- **Not secure** as subject to **brute force attacks** due to a **lack of password lockout logic**, as such is discouraged and **disabled by default**