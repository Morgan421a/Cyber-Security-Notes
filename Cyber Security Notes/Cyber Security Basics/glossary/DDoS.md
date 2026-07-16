Distributed Denial of Service

- Flooding a server, service or network with an overwhelming amount of internet traffic from multiple sources, making it unable to process legitimate requests
- Like a data traffic jam
- Typically done using something like a botnet of compromised devices
- Theoretically possible and does happen -> An attacker can silently infect multiple devices in an org using something like a dormant malware whereby devices show no signs of infection until a specific command is received.
	- Once triggered can be used to launch a DDoS attack against an external target or even the org's own internal network (insider DDoS)
	- Difficult to detect since traffic is originating from within the trusted network so outer firewalls might not block it immediately.
- Dark DDoS - Using a DDoS attack like a smokescreen to distract the Blue Team of an organisation while carrying out  more malicious attacks such as stealing data from elsewhere in the organisation or installing ransomware etc.
- Methods of defence against DDoS attacks include:
	- Traffic scrubbing - rerouting traffic through a scrubbing centre, typically provided by ISPs or CDN services, which filter out malicious packets and only send clean traffic to a server
	- Rate Limiting & Filtering - Configuring firewalls and Load Balancers to drop traffic from suspicious IP ranges or limit the number of requests per second
	- Blackholing - Dropping traffic to the target IP entirely (null-routing) to save the rest of the network. Basically takes service offline to prevent a total collapse. *Typically only used in extreme cases*
