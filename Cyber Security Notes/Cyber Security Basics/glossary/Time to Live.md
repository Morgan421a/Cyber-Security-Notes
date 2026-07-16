---
aliases:
  - TTL
---
- Sets packet expiry timer to prevent clogging of network if it fails to reach host or escapes
	- IPv4 - represented as seconds by definition but **hop count** in practice
	- IPv6 - field explicitly renamed to **Hop Limit**, no time based definition

- Sets DNS Record lifetime in a Recursive DNS Server and a Device's local cache 
	- TTL represented as a 32-bit integer in units of seconds 

