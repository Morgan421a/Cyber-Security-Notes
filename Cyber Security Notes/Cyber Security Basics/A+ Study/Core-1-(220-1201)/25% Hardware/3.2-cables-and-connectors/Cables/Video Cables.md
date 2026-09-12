### HDMI (High-Definition Multimedia Interface)
- A **Protocol** **and** a **Connection**
- **Video and Audio** stream
	- **Digital connection**, no analog
	- **~20 metre distance** before losing too much signal
	- Supports **resolutions up to 8K**
	- **Refresh rates** of **60, 120, 144** Hz
	- **HDCP (High-Bandwidth Digital Content Protection)** for secure transmission of copyrighted content
##### Connector Types:
- **19-pin (Type A) connector**
	- **Standard full-size HDMI** connector used in most devices
	- One of the most common video connector types
- **Type C Connector**:
	- **Mini HDMI** for compact devices such as cameras
- **Type D Connector**:
	- **Micro HDMI** for portable devices like smartphones
##### Cable Categories
- **Standard (Category 1)**:
	- Supports up to 1080p resolution
- **High-Speed (Category 2)**:
	- Supports up to 4K & 8K resolution
	- Speeds up to 48 Gbps

### DisplayPort
- A **Protocol** **and** a **Connection**
- **Digital Information sent in the form of packets**, similar to Ethernet and PCI Express (PCIe)
	- Carries both **audio and video**
	- Supports 4K resolution and beyond
	- Data transfer speeds up to 20 Gbps
- **Compatible with HDMI and DVI**
	- Passive adapter can be used to convert:
		- DisplayPort -> HDMI
		- DisplayPort -> DVI
- **Full-sized display port** may include a **locking mechanism**
	- Needs to be unlocked before attempting to remove from a port <- Often has a button on the top or sides of the connector
	![[Pasted image 20260831105847.png|184]]

### DVI (Digital Visual Interface)
- A **Protocol** **and** a **Connection**
- Often found on older systems
- Limited to 1080p resolution
- **No native audio support**
- Single connector type with multiple types of connections:
	- **DVI-A**:
		- **Analog Signals**, Backwards compatibility with VGA
	- **DVI-D**:
		- **Digital Signals**
		- **Single Link** = **3.7 Gbps** (1920 x 1200 at 60 Hz)
		- **Dual Link** = **7.4 Gbps** (2560 x 1600 at 85 Hz)
		- No Audio Support
	- DVI-I:
		- **Integrated** <- **Digital** and **analog** signals in the **same connector**
		- **Single Link** = **3.7 Gbps** (1920 x 1080 at 60 Hz)
		- **Dual Link** = **7.4 Gbps** (2560 x 1600 at 85 Hz)
	![[Pasted image 20260831110827.png|201]]

### VGA (Video Graphics Array)
- A **Protocol** **and** a **Connection**
- **DB-15** Connector
	- More accurately **DE-15**
	- 15-Pin D-sub connector
- Carries analog signals for red, green, and blue separately
- Max resolution up to 640x480 pixels
- **Often** have a **Blue colour**
	- According to **standardised colours** in the **PC System Design Guide**
- **Video Only**, **No Audio**
- **Analog Signal**
	- **Image degrades after 5 - 10 metres**
 ![[Pasted image 20260831111239.png|315]]

### USB-C
- **A Connection, Not A Protocol**
- Supports **video, data**, and **power delivery**
- Supports **DisplayPort Alternate mode (alt mode) for video transmission**
	- Can support 4K and 8K video resolutions <- Ensure **cable supports** desired resolution
- Supports different **refresh rates**: **60, 120, 144** Hz <- Dependent on what **cable supports**
- **Longer cable may degrade signal qualities**, especially for high-speed connections
- Many uses, including:
	- Power
	- USB Data
	- Thunderbolt Data
	- DisplayPort Video
	- HDMI Video (Not Common)
	- Mobile High-Definition Link (MHL)
- Can use **Alt Mode** for **transmitting non-USB signals** such as DisplayPort video, Thunderbolt, or HDMI

### Thunderbolt
- High speed interface that **supports video, data** and **power** over a **single connection**
- **Compatible** with **DisplayPort** and **USB-C devices**
- **Short cable lengths** <- Up to **0.5 metres for max speeds**
- **Versions**:
	- **Thunderbolt 1 and 2**:
		- Use Mini DisplayPort Connectors
	- **Thunderbolt 3 and 4**:
		- Use USB Type-C connectors <- speeds up to 40 Gbps
