Address Resolution Protocol

- ARP Request - Broadcast to network when device wants to communicate with another asking which MAC addy owns the target IP
	- Only device that owns target IP will respond with an ARP Reply
	- ARP reply - Device with matching target IP replies with its MAC addy

- If the destination is on a different network, ARP will forward frames to the router's MAC address (Default Gateway)
