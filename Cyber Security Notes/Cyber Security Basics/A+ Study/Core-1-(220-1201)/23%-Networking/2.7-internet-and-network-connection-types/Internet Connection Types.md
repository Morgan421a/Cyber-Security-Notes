### Satellite Networking
- **Communication with a satellite** <- Allows for **connection** to the **internet** from **almost** **anywhere**
	- Sometimes referred to as **"Non-terrestrial" communication**
- **High cost** relative to terrestrial networking
	- **100 Mbit/s down, 5 Mbit/s up are common**
	- Good for remote sites or difficult to network sites where a traditional form of internet connectivity isn't possible
- Has a relatively high latency due to the distance across which signals need to be sent (into space and back to Earth)
	- Some systems have **250 ms up, 250 ms down** (half a second of latency per packet)
	- **Starlink** advertises **25 to 60 ms**
- Not always the best option
	- **Requires line of sight**
	- **Rain Fade** <- Signal encounters rain, snow, ice or a storm in its path which may affect signal strength

### Fibre
- **High speed** data communication
	- **Uses light** (instead of electricity) **to transmit data**
		- Higher bandwidth
		- Longer distances without signal loss
		- Immune to Electromagnetic Interference **(EMI)**
- A lot of data sent through a small fibre
- High efficiency
- **More expensive** to install than **copper**
	- Equipment more costly
	- More difficult to repair
- Able to **communicate** over much **longer distances** than **copper**
- Good for Wide Area Networks (WAN)
	- Supports high throughput
	- **Synchronous Optical Networking (SONET)** <- Standardised protocol for transmitting large amounts of data over fibre optic cables at high speeds over long distances
	- **Wavelength Division Multiplexing (WDM)** <- Technique that allows a single fibre optic cable carry multiple separate signals at the same time by sending each one on a different wavelength (basically a different colour) of light.
- Now used for businesses and homes
- Different types of fibre:
	- **Single-mode fibre (SMF)** = **One light path**, used for **long-distance travel** (e.g. WANs, ISP backbones), Typically uses a **yellow jacket**
	- **Multi-mode fibre (MMF)** = **Multiple light paths**, used for shorter distances (e.g. within a building/campus), Typically uses **Orange** or **Aqua Jacket** 
- ISP's often use **Deployment Terms**:
	- **FTTH/FTTP** (Fibre to the Home/Premises) = Fibre goes all the way to the customer
	- **FTTC/FTTN** (Fibre to the Curb/Node) = A **Hybrid Setup**; Fibre goes partway, copper/coax finishes the final stretch
### Cable
- **Broadband**
	- Transmission across **multiple frequencies** with **different traffic types** **simultaneously**
- Plugged into a **cable modem**
	- Accesses the local network through Ethernet connection
- Efficient method to provide Voice, Video, and Data communication for a home
- **DOCSIS (Data Over Cable Service Interface Specification)**:
	- **Standard** used to transmit data over a broadband network
	- Different versions of DOCSIS providing different levels of service and connection speeds
- **High speed** networking
	- **50 Mbit/s through 1000+ Mbit/s (1 Gigabit)** are common

### DSL
- **Digital Subscriber Line (DSL)**
	- Sometimes referred to as **Asymmetric Digital Subscriber Line (ADSL)**
- **Asymmetric**:
	- Download speed faster than upload speed
	- **200 Mbit/s downstream, 20 Mbit/s upstream** is common
	- **~10,000 foot** (~3000 metres) **limitation** from the **central office (CO)**
	- Potentially **faster** **speeds** if **closer** to the **CO**
		- **Central Office** = Physical location (telephone company's building) that sits between the DSL modem's location and an ISP's core network

### Cellular Networks
- Separates land into **"cells"**
	- **Antennas** cover a **cell** with **certain frequencies**
- Used by **mobile phones**, hence the nickname **"Cell phones"**
- **Tethering** = Turning a phone into a **wireless router** to **provide** a **single** other **device** with **internet connectivity**
	- **1 - 1 connection**
	- Must be supported by mobile carrier, may incur additional costs
- **Mobile Hotspot** = Turning a phone into a **wireless router** to provide **multiple** other **devices** with **internet connectivity**
	- Must be supported by mobile carrier, may incur additional costs

### WISP
- **Wireless Internet Service Provider (WISP)**
- **Terrestrial** internet access using wireless
- Useful for **rural/remote locations** where other types of ISP connection aren't available
- Easy to setup
	- Only needs an outdoor antenna to access the **WISP**'s network
- Many **different deployment technologies**:
	- **Meshed 802.11** <- Same type of 802.11 connection used in homes and businesses
	- **5G Home Internet** <- Using a mobile phone provider as the ISP
	- **Proprietary Wireless**
- **Speeds** can range from:
	- **~10 Mbit/s to 1,000 Mbit/s**