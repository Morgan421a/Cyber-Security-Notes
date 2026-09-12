### USB (Universal Serial Bus)
- Provides both **power and data transfer capabilities**
	- Supports multiple devices via **Daisy-Chaining** <- Allows up to 127 devices connected to a single port
	- **Bandwidth shared across** all **devices** connected to **same USB port** <- more devices = less speed for each
- Standard connection types for most devices that connect to a computer, such as:
	- Keyboards, mouse, printers, storage devices, etc.
#### USB Versions and Speeds
- **USB 1.1**:
	- **Low Speed USB: 1.5 Mbit/s**, generally **3 metres cable length** <- defined by USB 1.0 specification
	- **Standard** called **Full Speed USB:
		- **12 Mbit/s**
- **USB 2.0**:
	- **Standard** called **High-Speed USB**:
		- **480 Mbit/s**
- **USB 3.0**:
	- **Standard** called **SuperSpeed**:
		- **5 Gbit/s**
- **USB 3.1** Gen 2:
	- **Standard** called **SuperSpeed+ USB**:
		- Maximum **10 Gbit/s**
- **USB 3.2** USB Gen 2x2:
	- Maximum **20 Gbit/s**
- **USB 4.0**:
	- Maximum **40 Gbit/s**
#### Distance Limitations
- **USB 1.0**:
	- **3 Metre** Cable Length
- **USB 1.1 & 2.0**:
	- **5 Metre** Cable Length
- **USB 3.0 and later**:
	- Commonly **3 Metre** Cable Length
	- Standard doesn't specify an exact cable length
	- **Maximum Practical Cable Length for 3.x = 5 Metres**
- **Using Longer cables** can result in **signal deterioration** and **reduced speeds**
#### Power Delivery
- **USB 1.0 & 2.0 Ports**:
	- **Max power output = 500 mA (0.5A)**
- USB 3.0 Ports:
	- **Max power output = 900 mA (0.9A)** <- equates to **4.5 watts**
- **Dedicated USB ports labelled** as **PD** (Power Delivery) can provide **up to 1.5A (7.5 watts)**
- Higher USB versions offer better power delivery capabilities

### USB 1.1/2.0 Connectors
- **Standard-A Plug** <- **Still commonly used**; typical USB plug
- **Standard-B Plug** <- Often **used for peripherals** such as printers or other **external devices**; more square shaped connector
- **Mini-B Plug** <- Often used for mobile devices
- **Micro-B Plug** <- Often used for mobile devices
![[Pasted image 20260831102206.png|463]]

### USB 3.0 Connectors
- **USB 3.0 Standard-A Plug** <- Same form as previous versions' Standard-A Plug
- **USB 3.0 Standard-B Plug** <- Slightly taller than previous version
- **USB 3.0 Micro-B Plug**
![[Pasted image 20260831102443.png|465]]

### USB-C
- Created to essentially **replace** all **other USB connector types**
- **USB-C describes the physical connector, not the signal**
- Can be inserted either way around unlike previous versions
 ![[Pasted image 20260831102700.png|331]]

### Serial Cables
- Used before USB
- Many different formats, most popular being:
	- **DB-9** <- "9" refers to size of connector, **9 pins**, sometimes referred to as **DE-9**
	- **DB-25** <- **25 pins**
- Letter refers to connector size
- Commonly used for **RS-232**
	- **Recommended Standard 232**
	- Industry standard since 1969
- Serial Communications standard
	- Built for modem communication
	- Used for modems, printers, mice, networking
- Now used as a **configuration port**
	- Typically seen on legacy equipment (**Serial/Console port**)
- Allows a user to directly connect to the device through the console port
	- Traditionally a serial connection
	- Can be a DB9 connector, RJ-45 serial, USB connection
- **Console connection** will be **available when no other connection methods** are **available** through the **serial interface**
	- Typically a **text-based serial interface** interacted with through the console
- Modern devices likely need a **USB to DB9 serial adapter**

### Thunderbolt
- **High-speed serial connector** that carries **data** and **power** on the **same cable**
- Based on Mini DisplayPort (MDP) Standard
- Has had **multiple versions**:
	- **Thunderbolt 1**:
		- **Mini DisplayPort Connector**
		- **2 Channels** of throughput:
			- **10 Gbit/s per channel** <- 1 channel per device
			- **20 Gbit/s total throughput**
	- **Thunderbolt 2**:
		- **Mini DisplayPort Connector**
		- **20 Gbit/s aggregated channels** <- 1 device can use full 20 Gbit/s
	![[Pasted image 20260831104220.png|248]]
	- Mini DisplayPort Connector
	- **Thunderbolt 3**:
		- **USB-C** Connector
		- **40 Gbit/s Aggregated** throughput
		- Maximum cable length **3 metres** (**copper** cable)
			- **60 metres** (**optical** cable)
		- Devices can be daisy chained rather than all needing to be plugged directly into the main device
	- **Thunderbolt 4**:
		- Still **40 Gbit/s aggregated** throughput
		- **Support for dual 4K displays**
		- Increased **PCIe bandwidth** <- allows more data to be transferred from the motherboard to peripheral devices

### Overall USB Version Stats

|            | 1.0                       | 1.1                                      | 2.0                       | 3.0                       | 3.1                       | 3.2                       | 4.0                       |
| ---------- | ------------------------- | ---------------------------------------- | ------------------------- | ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| Speed      | 1.5 Mbps                  | Low Speed: 1.5 Mbps, Full-Speed: 12 Mbps | High-Speed: 480 Mbps      | SuperSpeed: 5 Gbps        | SuperSpeed+: 10 Gbps      | 20 Gbps                   | 40 Gbps                   |
| Max Length | 3 m                       | 5 m                                      | 5 m                       | Often 3 m, up to 5 m      | Often 3 m, up to 5 m      | Often 3 m, up to 5 m      | Often 3 m, up to 5 m      |
| Power      | 500 mA (0.5A) (2.5 watts) | 500 mA (0.5A) (2.5 watts)                | 500 mA (0.5A) (2.5 watts) | 900 mA (0.9A) (4.5 watts) | 900 mA (0.9A) (4.5 watts) | 900 mA (0.9A) (4.5 watts) | 900 mA (0.9A) (4.5 watts) |
