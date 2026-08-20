### Wireless Technologies
- **IEEE Standards** 
	- Institute of Electrical and Electronic Engineers
	- **802.11 Committee**
		- Develops and maintains standards for **Wireless Local Area Networks** (WLANs) AKA **Wi-Fi**
- 802.11 tends to be referenced to by its generation to make differentiating between versions easier:
	- **802.11ac** = Wi-Fi 5
	- **802.11ax** = Wi-Fi 6 and Wi-Fi 6E (Extended)
	- **802.11be** = Wi-Fi 7
	- Future versions will increment accordingly

### 802.11 Technologies
- Wi-Fi networks have different frequencies that they can use for communication
	- Different standards of Wi-Fi use different frequencies
- Most Wi-Fi networks use frequencies in the ranges of:
	- **2.4 GHz**
	- **5 GHz**
	- **6 GHz**
	- Some access point and devices can communicate across multiple ranges at the same time
- 802.11 committee have grouped frequencies together into channels
	- **Channels** = Groups of frequencies that are numbered by the IEEE (e.g. channel 44 used for 5 GHz range <- specific range = 5.220 GHz)
	- Frequencies managed by governing entities
	- Each channel = 20 MHz wide (Bandwidth)
	- Each channel numbering is 5 MHz apart e.g. channel 1's centre frequency is 2412 MHz and channel 2's centre frequency is 2417 MHz
	- Best to use a Wi-Fi channels whose centre frequencies are separated by at least 20 MHz to prevent overlap which would degrade performance
		- In the 2.4 GHz range, channels are numbered 5 MHz apart 
			- Channels **1, 6, and 11** (each 5 slots apart) have centres 25 MHz apart which clears the 20 MHz threshold and results in no overlap
- Bandwidth = The amount of frequency in use for communication
	- Commonly seen bandwidths are:
		- 20 MHz
		- 40 MHz
		- 80 MHz
		- 160 MHz

### Band Selection and Bandwidth
- 2.4 GHz range typically limited to only 3 channels on a 20 MHz bandwidth <- led to a lot of interference in places where a lot of wireless devices were being used
- 5 GHz range has many more frequencies available on bandwidths 20 MHz, 40 MHz, 80 MHz, and 160 MHz <- More bandwidth = higher throughput
- 6 GHz range has a lot more frequencies available on bandwidths 20 MHz, 40 MHz, 80 MHz, 160 MHz, and 320 MHz <- Even higher throughput

### Bluetooth
- Uses 2.4 GHz range
- Sometimes referred to as the **Unlicensed ISM (Industrial, Scientific, and Medical)** Band
	- Unlicensed ISM band = Frequencies which don't require special licenses to use them 
		- Meaning devices can be connected to other devices using 802.11 or Bluetooth freely
- Short range (Personal Area Network)
	- Most consumer device range around 10 metres

### RFID - Radio-Frequency Identification
- Used everywhere:
	- Access Badges
	- Inventory/Assembly line tracking
	- Pet/Animal identification
	- Anything that needs to be tracked
- Use Radar Technology:
	- Radio Energy transmitted to tag
	- Radio Frequency powers the tag, ID is transmitted back
	- Bidirectional communication (Both the tag and device they're used for communicate with each other)
	- Some formats can be active/Powered

### NFC - Near Field Communication
- Two-way wireless communication
	- Builds on RFID <- RFID tends to be one-way
- Popularly used for: 
	- Payment systems via online wallets across major credit cards
	- Identity tokens for ID or unlocking doors
- Bootstrap for other wireless
	- NFC helps with Bluetooth pairing by working with the connection target (e.g. phone) to provide the pairing device (e.g. airpods) with the necessary configuration parameters needed to connect to the network