### IP - Internet Protocol
- Network topology = road through which data travels
	- e.g. Ethernet, DSL, Cable system, etc.
- Every computer on a network has an IP address
	- Identifies a computer on a network and differentiates computers on the same network
	- When data sent to a webserver, the data is sent to its specific IP address

### TCP and UDP
- Transported inside of IP
	- Encapsulated by the IP protocol
- Two different ways of moving data from place to place
- TCP = Transmission Control Protocol
- UDP = User Datagram Protocol
- Typically referred to as a layer 4 protocol in networking
- Allow for Multiplexing
	- Multiplexing = Communicating across multiple devices at the same time and potentially send information that is different from each other

### TCP - Transmission Control Protocol
- Connection-oriented:
	- Uses a process (Three-Way-Handshake: SYN, SYN-ACK, SYN) to setup a connection between devices
	- Also uses a process (Four-Way-Handshake: FIN, ACK, FIN, ACK) to close a connection between devices
- Considered "**reliable**" delivery
	- Can recover from errors
	- **Can re-order** data if needed or **re-transmit** it
	- Includes an acknowledgement process (i.e. Client: TCP Data -> Target Host, Target Host: ACK -> Client)
	- An instance of missing or "damaged" data can be communicated back to the client by the target host, informing them of an issue and that the data needs to be sent again
- Allows for flow control <- Target Host can tell Client to adjust the speed at which data is sent depending on how much information the target host can receive at a time
##### Communication Using TCP
- Connection-oriented protocols prefer a "return receipt"
	- HTTPS (Hypertext Transfer Protocol Secure)
	- SSH (Secure Shell)
	- Re-sends data automatically using the TCP protocol
- App doesn't need to be concerned regarding out of order frames or missing data
	- TCP handles all of the communication overhead

### UDP - User Datagram Protocol
- Connectionless
	- No formal open or close to the connection
- Considered "**unreliable**" delivery
	- Lacks error recovery
	- **Doesn't** **reorder** data or **re-transmit** it
	- No acknowledgements -> Client doesn't know if target host received the data properly
- No Flow control <- Client determines speed at which data is transmitted
	- No acknowledgement messages -> target host can't inform if too much or too little is being sent at once
##### Why use UDP?
- Little overhead, no need to setup a connection between client and host unlike TCP means UDP has lower resource usage
- Good for real-time communication apps
	- e.g. video streaming, voice over IP related apps, online games (e.g. CoD multiplayer) etc.
	- No way to resend data
- Connectionless Protocols that use UDP
	- DHCP (Dynamic Host Configuration Protocol)
	- TFTP (Trivial File Transfer Protocol)
- Apps can provide data re-sending functionality by keeping track of what is sent between the client and host and can decide if any data needs to be re-sent across the network
	- App must be able to manage this process, **not done by default**
	- Some apps (e.g. Voice over IP), might not do anything if data is lost, it just keeps sending traffic

### Ports
- **Port** = The specific point on a computer through which data is sent/received
	- Different ports have different numbers (0 - 65,535)
- When data is sent from one device to another, there are typically 3 important bits of information:
	- Host/Client IP Address
	- Protocol (e.g. TCP/UDP)
	- Host (e.g. server application)/Client Port Number
- **Non-Ephemeral** Ports AKA **Permanent Port** Numbers:
	- Some apps always tend to use the same port numbers 
	- Ports **0 - 1023**
	- Usually used on a server or service
- **Ephemeral Ports** AKA **Temporary Port** Numbers:
	- Typically Ports **1024 - 65,535**
	- Determined in real-time by the client
##### Port Numbers
- TCP and UDP ports can be any port between 0 - 65,535
- Most **Servers** (Services) use **non-ephemeral** (not-temporary) port numbers
	- Common but not **always the case**
- **Used for Communication, Not Security**
- Service Port Numbers need to be "well known" -> Port number must be known to communicate to particular service hence the reasoning behind using non-ephemeral ports
- TCP and UDP port numbers aren't the same i.e. TCP port 80 is different from UDP port 80