- PCs and Laptops can also be connected to networking devices via a **console cable** or a **USB cable**
	- Older PCs and laptops connect via an **RS232 Port** (looks similar to VGA)
	- Modern PCs and laptops typically connect via **USB ports**, often no longer have an RS232 port
	- Connection provides **management access** <- Used to view and change device configurations
	- Console Cable:
		- Almost always **RJ45** on one end (Device side, for standard enterprise routers/switches)
		- Computer side:
			- **DB9** for old PCs or used with a USB adapter
			- **USB** for modern laptops (adapter built-in)
			- **RJ45** for use with a separate adapter or wall jacks

- **.pka file** <-Packet tracer activity file, have instructions window and activity scoring
- **.pkt file** <- created when a simulated network is built in packet tracer and saved, can have graphic background images embedded within it, no instructions window or activity scoring
- **.pksz file** <- Specific to Packet Tracer Tutored Activities (PTTA), bundle a .pka file, media assets, and scripting assets for the hinting system
- **.pkz file** <- **Deprecated** file type, used to be used to embed images and other files in a packet tracer file

- **Cable modem** <- hardware device that allows communications with an ISP
	- **Coaxial cable from the ISP** is connected to the **cable modem**, and an **Ethernet cable** from the local network is also connected
	- **Cable modem** **converts** the **coaxial** connection **to** and **Ethernet** connection

- Initial **Pink Packets sent from switches**:
	- Called **Bridge Protocol Data Units (BPDUs)**
		- **Layer 2 protocol** messages used by switches to run **Spanning Tree Protocol (STP)** to **prevent network loops**
	- **PortFast** can be configured to tell switch a specific port connects to an end host (not another switch) so it skips the STP convergence timers, in packet tracer it can be done through a switch's CLI as such:
		- Single interface: `interface <interface_number>`
						`spanning-tree portfast`
		- All interfaces at once: `spanning-tree portfast default`
		- **Must be in `config` mode to do either**