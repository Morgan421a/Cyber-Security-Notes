---
aliases:
  - IV
---
- **Initialisation Vector**
	- Per packet value combined with the secret key to generate a unique RC4 keystream for each packet, ensuring that identical plaintext produces different ciphertext every time
		- IV is transmitted unencrypted
		- Example in WEP frame:
			- `[IV (24 bits)] [ciphertext] [ICV]`