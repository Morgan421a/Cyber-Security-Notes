### Cable Crimpers
- Used to **permanently "pinch"** the end of a **connector** **to** a **cable**, for example:
	- Coaxial: Attaches RG-6 or RG-59 connectors
	- Twisted Pair: Secures RJ-45 connectors
- **Commonly** used to connect and **RJ-45 connector** onto a **twisted cable**
	- In other words -> To connect the **modular** **connector** to the **Ethernet cable**
	- The final step of the process
- For twisted pair wires **Metal prongs** are pushed **through** the **insulation** to **connect** directly to the **copper** **inside** of the **connector**
	- Plug permanently pressed onto the cable sheath

### Snips and Cutters
- Used to **cut cables** from spools or bundles
- Often **durable** enough to cut twisted pair, coaxial or other cable types

### Cable Strippers
- Used to **remove** the **outer jacket (insulation)** of **cables** to **expose** the **inner wires**
- Example uses include:
	- Twisted Pair Cables: Preparing wires for RJ-45 Connectors
	- Coaxial Cables: Revealing centre conductor by stripping metal braiding and jacket

### Modular Connectors
- Before crimping copper connector stick up slightly and have sharp prongs on the bottom
	- Prongs are what push through the insulation to connect directly to the copper wire inside
- After connecting, prongs move down and prongs can be seen pushed through the insulation of the wire inside
- Often have a cable stay on the open side of the connector to reduce the ease of the cable being pulled out once it has been crimped

### Crimping Best Practices
- Get a **good**:
	- **Crimper**
	- **Cable snips/cutters** <- Sometimes called **electrician's scissors**
	- **Wire strippers**
- Ensure the correct modular connectors are being used
	- Different wire types use different connectors

### Wi-Fi Analyser
- **Hardware** based Wi-Fi analysis
	- Avoids the limitations of operating systems
	- Allows all 802.11 information in the air to be viewed
- Displays various types of **Wi-Fi Information**, such as:
	- **Frequencies/channels** currently in use on current and surrounding networks
	- **Signal Strength** from a local access point
	- **Access Points** 
	- **Interference** occurring across a network
	- **Wireless Devices** communicating to the access point
#### Spectrum Analyser
- Provides **more frequency information** than a Wi-Fi analyser
	- Useful when many different devices are part of a larger picture
- Can show any frequencies that are currently in use by other devices nearby

### Tone Generator
- **Traces Cables through walls or ceilings**
- Uses **two parts**:
	- The **Tone Generator itself** <- **Plugs** **into** a **wire** and **generates** an **analog sound** onto the wire
		- The **Analog Sound cannot be heard by humans**. as such an:
	- **Inductive Probe** <- Is used to **hear** the **analog sound through** a **small speaker**
		- Doesn't need to touch the copper
- Easily allows the ends of a wire to be found, even in complex environments
1. Connect Tone generator to the wire
	- Can be through a modular jack (e.g. RJ-45 connector), Coax connector, or directly into the punch down block
2. Use probe to locate the sound by moving from wire to wire

### Punch Down Tool
- Used to **"Punch"** a **wire** **into** a **wiring block/punch-down block/patch panel**
- Every wire must be **individually punched**
- **Fastens wires** to prevent them from being pulled out easily
- Often **trims wires** **during** the **punch**, assisting in a clean installation
- Example uses:
	- **66 Block**: Often used for **analog phone** cabling
	- **110 Block**: Often used for **network** cabling or **wall jacks**

### Punch-Down Best Practices
- **Keep wires** and their respective blocks **organised** due to the large number of wires used
	- Ensure good cable management
- Maintain cable twists into the punch down block to help prevent interference by keeping the network signal strong
- Document Everything
	- Written Documentation
		- Note where each cable is going <- Helps in recognising what number each cable is punched-down into and where the other end of the cable is
	- Tags
	- Graffiti

### Cable Testers
- Used to **ensure** everything is **wired** **properly** on a **cable**
- Ensures **continuity** between all pins
- In the context of a **patch cable**:
	- Pin 1 should connect to pin 1, pin 2 to pin 2, and so on
- Can **identify** **missing pins** as well as **crossed wires**
- Not typically used for frequency testing due to crosstalk, signal loss, etc.
- Diagnoses issues such as:
	- **Open Pair** = Conductors not connected
	- **Short** = Conductors touching within the cable
	- **Reverse Pair** = Wires connected to opposite pins
	- **Cross Pair** = Wires of one pair connected to another pair's pins
	- **Split Pair** = Wire from one pair crosses into another pair
#### Cable Certifiers
- Used to **Determine cable category, throughput** and **length**
- **Measures** **resistance** and **delay** for **performance reports**

### Loopback Plugs
- A **cable that loops back into itself**
- **Test Network Ports** by **rerouting** the **transmit** **signal** to the **receive** **pins**
	- Can also be used to trick apps
- Example uses:
	- **Ethernet**: Connects pin 1 to pin 3 and pin 2 to pin 6 in RJ-45 connectors
	- Fibre Networks: Use patch cables for diagnostic testing
- **Different plugs** exist for different connections such as:
	- Serial / RS-232  (9 pin or 25 pin), Ethernet , T1 , Fibre, etc.
- **Not Cross-Over Cables**
1. Plug into device interface and set interface into a diagnostic mode
2. Diagnostic mode sends data out of the interface and checks if any data is being looped back into the received part of the interface
3. If everything is working correctly, data received should match the data that was sent
4. If any difference between data sent and data received is seen, there is likely a problem with the physical port

### Taps and Port Mirrors
- Used to **intercept network traffic** and **send** a copy **to** a **packet capture device**
- Used for tasks such as network monitoring, intrusion detection, packet capture/troubleshooting, etc.
#### **Physical Taps**:
- Disconnect a link and put the tap in the middle of the link
- Can be an **Active Tap** = Requires a power source, typically **copper taps**
- Or can be a **Passive Tap** = Don't require any power, often **fibre taps**
#### **Port Mirror**:
- Also called a **Port Redirection** or a **SPAN (Switched Port ANalyser)**
- **Software-based Tap**
- **Network analyser plugged** into one **port**, **instruct switch** to take data from another interface and **copy** the **frames** **into** the **protocol analyser port**
- **Limited functionality**
