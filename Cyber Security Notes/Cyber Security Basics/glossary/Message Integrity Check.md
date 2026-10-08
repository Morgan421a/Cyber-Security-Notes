---
aliases:
  - MIC
---
- **Message Integrity Check (MIC)**
	- Used to Prevent attacks on encrypted packets (called bit-flip attacks) by adding a few bytes to each packet to make them tamper proof
		- Bit-flip attack = intruder intercepts encrypted message, alters it, and re-transmits it to the recipient
		- MIC implemented on access point, and all associated client devices