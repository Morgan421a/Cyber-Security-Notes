**Car Park:**
- Elaborate -> One of the main benefits of the OSI model is that devices can have different functions and designs on a network while communicating with other devices => ==allows completely different devices from different manufacturers to communicate with each other==
- What is meant by the receiving endpoint? is it the target host device? => ==Yes==
- Do routers use ping checks to check path speed and reliability? => ==No, only in a specific circumstance==
- GUI = a software? -> ==Yes = software component meant to function as apart of larger software or systems (i.e. an OS)==
- UDP is flexible to software developers = ==bare-bones, developers must build necessary advanced functionality if software requires it, good for dev customisation, bad for complexity==

**What is the OSI Model?**
- Used in networking
-  Provides a framework that controls how devices on a network send, receive and interpret data
- Occurs twice for data transfer, once when sending data (7 - 1) and again when the target host receives the data (1 - 7)
- Made up of 7 layers (arranged 7 - 1), each with different responsibilities, the layers are:
- 7. Application
- 6. Presentation
- 5. Session
- 4. Transport
- 3. Network
- 2. Data Link
- 1. Physical

- Specific processes occur at each layer data travels through in which info is added to the data (encapsulation)
-  Allows devices to have different functions and designs on a network while still communicating with other devices.
- Allows data sent across network following the model to be understood by other devices

**1. Physical**

- The physical components of the hardware used in networking i.e. Ethernet cables 
- Devices use electrical signals to transfer data between each other in a binary numbering system
- Lowest layer

**2. Data Link**
- Every network enabled computer has a [[NIC]] which comes with a unique MAC addy physically burned into it to identify it
- Data link carries out the physical addressing of a transmission by adding the MAC address of the receiving endpoint to the received packet from the network layer
- Physical MAC addy is what's used to identify where to send information not the IP addy
- Data link also presents the data in a transmittable format.

**3. Network**
- Where routing and data re-assembly takes place
- Routing determines most optimal path for data chunks to be sent
- Uses two protocols to determine which path is the most optimal:
1. OSPF (Open shortest path first)
2. RIP (Routing Information Protocol)

- Three factors used to decide which route is taken:
1. Shortest Path? I.e least num of devices for data to travel across? - RIP
2. Most reliable path? I.e Have packets been lost on path before? - OSPF
3. Faster physical connection? I.e Is one path using a copper (slower) or a fibre (much faster) connection? - OSPF

- Everything here is done using IP addies
- Devices that can deliver packets using IP addies are called Layer 3 devices. e.g. Routers

**4. Transport**
- Decides which protocol to use when transporting data:
1. TCP 
    - Reserves constant connection between the 2 devices for time needed to send data
    - Uses error checking to ensure data sent from small chunks (layer 5) has been received and reassembled in same order
    - Guarantees data integrity, is more reliable and can sync 2 devices to prevent data flooding into them 
    - Slower than UDP, requires a reliable connection between devices and can cause a bottleneck to another device since connection is reserved on the receiving computer the whole time
    - Example uses => file sharing, internet browsing, sending an email
2. UDP
	- No sync between 2 devices or guarantee
	- Useful when small pieces of data are being sent or larger files where some data can be lost
	- Faster than TCP, lets user software (layer 7) decide if there's control over the speed that packets are sent and doesn't reserve a continuous connection on a device
	- Doesn't care if data is received thus is less reliable, Flexible to software developers and means poor connections can lead to bad user experience
	- Example uses => small data like discovery protocols -> ARP (Technically layer 2) and DHCP; Large data -> Video streaming (pixelated footage, pixels = lost pieces of data)

**5. Session**
- Creates & maintains connection to target host once data arrives from layer 6
- Session = created when the connection is established
- Session stays active as long as connection does
- Responsible for closing connection if not used for a while or lost
- Sessions can contain checkpoints = if data lost only newest pieces of data need to be sent -> saves bandwidth
- Sessions = unique = data cannot travel across different sessions, only its own current one

**6. Presentation**
- Where standardisation happens
- Allows data to be handled the same way regardless of how software works (e.g. different email clients)
- Translates data to and from layer 7
- Understands data sent to device in one format destined to another device in a different format => Standardises data so it can be sent and reformatted to suit the receiving device's application format
- Where security features like data encryption (e.g. HTTPS) occur

**7. Application**
- Where rules and protocols regarding how users should interact with sent or received data exist
- Typically have a GUI for ease of interaction with sent or received data
- Another example of a protocol at this layer is DNS