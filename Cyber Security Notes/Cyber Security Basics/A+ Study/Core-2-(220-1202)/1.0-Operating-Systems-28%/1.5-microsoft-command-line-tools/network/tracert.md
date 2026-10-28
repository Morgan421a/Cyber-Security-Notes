- **`tracert <target IP or domain name>` <- Traceroute <- Determine the route a packet takes to a destination**
	- Maps the entire path
	- Uses ICMP TTL Exceeded error message
		- Time in TTL refers to hops, not seconds or minutes
			- TTL = 1 is the first router, TTL = 2 is the second router, etc.
	- Not all devices reply with ICMP Time Exceeded messages <- Some firewalls filter ICMP, may make it more difficult to determine where a router might be
		- ICMP is low-priority for many devices
	- Traceroute bounces back and forth between the sending device and routers along the way by using the ICMP TTL Exceeded messages
		1. First packet has a TTL of 1, goes to first hop, TTL - 1 = 0 meaning TTL exceeded
		2. Error message sent back to original device and displayed as hop count, time for round trip, and Router's IP address
		3. Traceroute sends packet out again but with TTL incremented by 1 so TTL = 2, packet travels 2 hops, TTL - 1 at first hop, TTL - 1 again at second hop, TTL exceeded at second hop and error message sent back to original device
		4. Process continues until target IP is reached, at which point host device sends an ICMP Reply back to original sending device
			- Process can stop early if manually interrupted or the max hops is exhausted (default of 30)
- `tracert /h 50 mydomain.com` <- Changes max number of hops to 50, **limit of 255 hops**
