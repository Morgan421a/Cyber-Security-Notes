**Car Park:**

****
**Packets and Frames**
- Packet = piece of data from layer 3, contains info like IP header and payload (the data intended to be sent)
	- Efficient method of transporting data between devices on a network cuz data exchanged in small pieces = less chance of bottlenecking
	- Structure differs depending on type of packet being sent, structure depends on protocols
	- IP based packets contain headers with extra info to data being sent called IP Headers:
		1. Time to Live (TTL)
		2. Checksum (Only in IPv4 not IPv6)
		3. Source Address - IP addy of device sending packet 
		4. Destination Address - IP addy of device to receive packet
		5. Protocol Type
- Frame = used at layer 2, encapsulates packet and adds info such as MAC addies

**TCP/IP (The Three Way Handshake**
- TCP/IP protocol consists of 4 layers (like a short version of OSI model):
	1. Application
	2. Transport
	3. Internet
	4. Network Interface
- Info added at each layer
- encapsulation = adding info to data ; decapsulation = removing info from data 
- TCP = Connection based = connection between client and server devices must be established before data is sent
- TCP packet has different headers added via encapsulation:
	1. Source Port 
	2. Destination Port 
	3. Sequence Number
	4. Acknowledgement Number
	5. Checksum Always mandatory in both IPv6 and IPv4 (Own version separate from IP header)
	6. Data
	7. Flags = URG, ACK, PSH, RST, SYN, FIN

- [[The Three Way Handshake]] - Used to establish connection between two devices
- Uses special messages to communicate:
	1. SYN - Sent by client to initiate connection and SYNc two devices together
	2. SYN/ACK - Receiving device (server) sends to ACKnowledge sync attempt from client
	3. ACK - Sent by either to ACKnowledge that a series of messages/packets have been received successfully 
	4. DATA - Message used to send DATA (i.e. bytes of a file) once connection is established
	5. FIN - Used to cleanly (properly) close connection after completion
	- RST - Ends all comms abruptly, last resort, indicates problem during process
- Sent data given random sequence number, used to reconstruct number sequence and increment by 1. 
- Both devices must agree on same sequence num for data to be sent in correct order. 
- Agreement done in three steps:
	1. SYN - Client gives initial sequence number (ISN) to SYNc with (0)
	2. SYN/ACK - Server gives own ISN to SYNc with (5000), and ACKnowledges client's ISN (0)
	3. ACK - Client ACKnowledges server's ISN and sends data which = Client ISN+1 (0 + 1)
- Best practice to close TCP connections ASAP cuz they reserve system resources on device
- TCP closes connection once device has determined other device has received all the data
	1. To initiate closure, device sends FIN packet to other device
	2. Other device ACKnowledges FIN packet and sends own FIN packet back to initial device
	3. Initial devices ACKnowledges connection closure request

**UDP/IP**
- UDP = Stateless protocol = no constant connection between the two devices (no three way handshake or sync between devices)
- Packets are simpler than TCP but shares some standard headers:
	1. Source Port 
	2. Destination Port 
	3. Checksum Mandatory in IPv6; Optional in IPv4 (Own version separate from IP header)
	4. Data 
- No acknowledgement sent between two devices during connection
- Client requests data and server sends data without checking if it arrived or not

**Ports**
- Points at which data can be exchanged
- Used by networking devices to enforce rules when communicating with each other
- Data sent or received is done through ports
- Ports = numerical value between 0 and 65535 (65,535)
-  Common Port = Ports between 0 and 1024
- Apps, software and behaviours are associated with standard set of rules for the sake of order. i.e enforcing web browser data be sent over by port 80, allowing web browsers to interpret data the same way as each other
- Other protocols include:
	- File Transfer Protocol (FTP) = Port 21
	- Secure Shell (SSH) = Port 22
	- HyperText Transfer Protocol (HTTP) = Port 80
	- HyperText Transfer Protocol Secure (HTTPS) = Port 443
	- Server Message Block (SMB) = Port 445
	- Remote Desktop Protocol (RDP) = Port 3389
- Possible to administer apps that interact with protocols on different port instead of the standard i.e running web server on 8080 instead of 80
- Apps will presume standard is being followed so colon (:) must be provided along with port number.

