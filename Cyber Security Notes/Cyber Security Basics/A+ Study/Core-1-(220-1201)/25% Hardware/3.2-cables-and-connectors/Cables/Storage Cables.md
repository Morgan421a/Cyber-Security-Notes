### SATA (Serial AT Attachment)
- Typically used to connect hard drives inside of desktop computers
- Device speed often the bottleneck, not the cable itself
- Has had multiple versions:
	- SATA Revision **1.0**:
		- SATA **1.5 Gbit/s**, 1 metre cable
	- SATA Revision **2.0**:
		- SATA **3.0 Gbit/s**, 1 metre cable
	- SATA Revision **3.0**:
		- SATA **6.0 Gbit/s**, 1 metre cable
	- SATA Revision **3.2**:
		- SATA **16 Gbit/s**, 1 metre cable
- **eSATA** (external SATA):
	- Similar functionality to internal drive <- matches the SATA version (e.g. SATA 3.0 eSATA = 6 Gbps)
	- Supports connecting an external drive over an **~2 metre cable**
- One **power cable** (**often 15-pin** connector), one **data cable** (**often 7-pin**, **L shape** connector)
-  **Power connector** plugs **directly** **into** **power supply (PSU)**
- **Data connectors** have **L-shape** in **centre** of their **port** on the motherboard
 ![[Pasted image 20260831113335.png|208]]

### eSATA Cable
- External Device Connections
	- Uses the SATA Standard
![[Pasted image 20260831113258.png|231]]

![[Pasted image 20260831113420.png|229]]

### Thunderbolt
- Up to 40 Gbps
- Short cable length <- under 2 feet (under 0.6 m)
- **Thunderbolt 3**: 
	- **Supports USB-C** devices
- **Thunderbolt 4**: 
	- Fully **compatible** with **USB 4**

### SCSI - Small Computer Systems Interface
- **Legacy** **Storage interface** for **connecting multiple devices**
- **Versions**:
	- **Narrow SCSI**:
		- Supports up to **7 devices**
	- **Wide SCSI**:
		- Supports up to **15 devices**
- Up to **320 Mbps**
- Connector Types:
	- **68-Pin high-density cable** <- Requires **separate power**
	- **80-Pin SCA** (Single Connector Attachment) <- Both **power** and **data** **combined**
- **Slower** than **modern SATA** and **SAS** Alternatives

### SAS - Serial Attached SCSI
- Modern enterprise grade **storage connection** used in **high-performance environments**
- Up to **24 Gbps**
- Supports **full duplex communication**
- **Backwards compatible with SATA drives**
- **Scalable** <- supports up to **128 devices per controller**
- Designed for **24/7 operation** while being **highly reliable**

