### Twisted Pair Copper Cabling
- **8 Individually insulated wires twisted into pairs**
- Two wires with equal and opposite signals twisted into pairs for balanced operation
	- Transmit+, Transmit- / Receive+, Receive-
- **Twists** keep a single wire constantly moving away from the interference, **reducing** **Electromagnetic Interference (EMI)** and **improving network performance**
- **More twists per inch** = **Better EMI protection** and **faster** data **speeds**
- The opposite signals are compared on the other end
	- What the real signal might be and what is likely the interference
- Pairs in the same cable have different twist rates

### Cable Categories
- Different cables may follow a different set of standards which define the minimum capabilities of each cable
- Cables don't have a speed but the electrical signals sent over a cable do
	- Signal encoding determines the data transfer rate
	- Minimum category of cable for transmitted signal must be used (e.g. cat 5e, cat 6, etc)
- A cable must be manufactured to specific standards
	- IEEE 802.3 Ethernet Standards determine the minimum cable type/category to be used for each type of signal
- Cable standards are described as a "category" of cable
	- Category 5e (cat 5e), category 6 (cat 6), etc.
	- IEEE standard should be checked to determine minimum cable category for a signal
	- Minimum cable category for 1000BASE-T (1,000 Mbps/1 Gbps)= cat 5
#### Copper Cable Categories
- **1000BASE-T** 
	- **Category 5**:
		- **100 metres** maximum supported distance <- Deprecated, mostly replaced by category 5e (enhanced)
	- **Category 5e (enhanced)**:
		- **100 metres** maximum supported distance
- **10GBASE-T** 
	- **Category 6**:
		- **Unshielded** = **55 metres** maximum supported distance
		- **Shielded** = **100 metres** maximum supported distance
	- **Category 6A (Augmented)**:
		- **100 metres** maximum supported distance
	- **Category 7**:
		- **100 metres** maximum supported distance
		- Can use RJ-45 or TERA connections
- **40GBASE-T**
	- **Category 8**:
		- **30 metres** maximum supported distance
			- Typically used in data centres
### Coaxial Cables
- **Coaxial** = Two or more forms sharing a common axis
	- The **inner conductor** and the **outer shield**
	- **Inner Conductor** = Carries the signals
	- **Outer Shield** = Protects signals running on the inner conductor
- Commonly used in networking for **cable modems/digital cable**
	- **RG-6** used in **television/digital cable** and **high-speed internet** over cable

### Unshielded and Shielded Cable
- **Unshielded Twisted Pair (UTP)**:
	- No additional Shielding
	- Most common twisted pair cabling
	- **Most widely used** due to **low cost** and **flexibility**
	- Easy to install, sufficient for most LANs
- **Shielded Twisted Pair (STP)**:
	- Additional **Shielding Protects against interference**
	- Each pair can be shielded or the overall cable can be instead
	- **Requires** the **cable** to be **grounded**  
		- So any **Electromagnetic Interference (EMI)** can be **discharged** such that it doesn't get induced into the wires carrying signals which may make the interference worse than unshielded cable
	- Good for high-interference environments like industrial areas
	- **More expensive** and **less flexible** than UTP
- Outer jacket of cable typically state what type of shielding is used in the cable, often in an abbreviated form:
	- U = Unshielded
	- S = Braided Shielding
	- F = Foil Shielding
	- Typically written and (Overall Cable Shielding) / (Individual pair shielding) TP
		- e.g. Braided shielding around entire cable and foil around pairs = S/FTP
		- e.g. Foil around cable, no shielding around pairs = F/UTP

### Direct Burial STP
- Overhead cable isn't always an option, instead the **cables** can be put **in the ground**
- Typically uses **specialised cables** that are designed to be placed in the ground
	- Designed to be **waterproof**
	- Often **filled with gel to repel water**
	- **Conduit** may **not** be **needed** <- Conduit = protective pipe/tubing used to protect cable from physical damage
- **Usually** a **Shielded Twisted Pair (STP)**
	- Provides Grounding, adds strength, and protects against signal interference
- Looks Similar to shielded Ethernet cable used in a network:
	![[Pasted image 20260831075133.png|396]]

### No Plenum
- Perceived ceiling in a building/office is likely a **drop ceiling** throughout which **air ducts** are typically placed
	- One duct forces an air supply into a room/building (Forced-air supply) 
	- Another duct forces air back out (Forced-air return)
- When the **area** around the **air ducts** is **empty** (dead/non-circulating airspace) it is referred to as having **no plenum**
### Plenum
- Similar setup to no plenum regarding air ducts, however **return air** is **sent** **into** the **empty space in** the **drop ceiling** as opposed to through a vent/duct system
- Carries **fire concerns**
	- Open space allows smoke and toxic fumes to travel freely and easily to other rooms in a building
	- As such **network cables** have been **specifically designed for** use in a **plenum** and **should be used** when running network cables through such a space
### Plenum-Rated Cable
- **Traditional Cable jackets** (e.g. standard ethernet cable) are often made of **Polyvinyl Chloride (PVC)**
- **Plenum-rated cables** are often made of **Fluorinated Ethylene Polymer (FEP)** or **Low-Smoke Polyvinyl Chloride (Low-Smoke PVC)**
- **Plenum-rated cable** often **not as flexible** as standard network cables
	- Lower bend radius
- Should **always plan for the worst case scenario** when considering the layout for any structure