### Computer Bus
- **Computer Bus = A pathway that connects motherboard components to each other and allows them to communicate**
	- e.g. A bus between the memory slots and the CPU, A bus that connects all of the expansion slots
- Allows the components to operate as a single unit
- Allow for system expansion which increase the capabilities of a device
- Example of the buses on a motherboard:
	![[Pasted image 20260904090300.png]]
	- Each line is an individual bus/pathway

### PCI
- **Peripheral Component Interconnect**
- Bus typically found on older motherboards
- Two **different sizes**:
	- **32-bit** bus width
	- **64-bit** bus width
- Sends data over a **parallel communication**
#### 32-bit PCI Bus
- 32 separate connections between devices
	- 1 bit sent across each of the 32 pathways simultaneously, 32 bits should all arrive to target device at the same time
![[Pasted image 20260904090654.png|279]]
- Example of a 32-bit PCI bus, each line = one pathway through which bits are sent
### 64-bit PCI Bus
- 64 separate connections between devices
	- 1 bit sent across each of the 64 pathways simultaneously, all 64 bits should arrive at target device at the same time
![[Pasted image 20260904090928.png|270]]
- Example of a 64-bit PCI bus, each line = one pathway through which bits are sent
### PCI 32-bit and 64 bit slots
![[Pasted image 20260904091041.png]]
- Top = 64-bit PCI bus(slot)
- Bottom = 32-bit PCI bus (slot)
- Traces running between them are connecting the bus connections together
- Each slot has a key to designate the power settings for the expansion cards plugged into the slots
	- e.g. 3.3V or 5V
	- Expansion cards have slots on the connectors to slide into the keys
		- 64-bit expansion cards have a separate key-way to designate that it's a 64-bit expansion card

### PCI Express (PCIe)
- Newer bus type
	- Replaced older PCI standard
- **Serial Communication**
	- Uses unidirectional serial "lanes"
	- Sends **1 bit at a time over the same pathway**
- different number of **full-duplex lanes** <- full-duplex = bi-directional data transmission (can be sent and received at the same time by devices)
	- **x1, x2, x4, x8, x16, x32** <- x pronounced as "by", e.g. by 1, by 2, by 4 . . .![[Pasted image 20260904092651.png|324]]
	- Example of a PCI Express by 1 lane <- 1 lane in one direction, one lane going the other
		- PCIe by 4 lanes would have 4 pairs of lanes, so 8 in total, 4 in one direction and 4 going the other
- **PCIe cards** still **have** a **notch** **to fit** into the **key of the PCIe slot** (slot tends to be on the opposite side of the standard PCI slots)
	- Also tend to have a **small hook on** the **back** of the interface card that **fits into a connector on the motherboard** <- helps to fasten the card to the slot and connects it to the motherboard