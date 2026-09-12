### WARNING
- **Always Disconnect A Device From the Power Source Before Working On It**
- **Some Devices Store A Charge In Capacitors And Need To Be Discharged Before Working With The Device**

### Computer Power Supply
- **Computers Use DC Voltage**
	- Most Power Sources Provide AC Voltage
- **Power Supply Converts AC** Voltage **to** **DC** Voltage using a transformer
	- e.g. **120V AC or 240V AC** gets **converted to** **3.3V DC**, **5V DC**, and **12V DC**

### Amp and Volt
- **Ampere (Amp/A)** = Rate of electron flow past a point in one second
	- e.g. The diameter of a hose pipe
- **Voltage (Volt, V)** = Electrical "pressure" pushing the electrons
	- e.g. How open the tap is

### Power
- Watt (W) = Measurement of real power use
	- **volts * amps = watts** / v * a = w / I * V = P (I = current/amps, V = voltage, p = power/watts)
		- e.g. 120V * 0.5A = 60W

### Current
- Power Supply details typically have specs for AC and DC power
- **Alternating Current (AC)** = **Current** that **constantly reverses direction**
	- **Distributes electricity efficiently over long distances**
	- **Hertz (HZ)** used to measure the **frequency of cycles per second**
	- **Frequency** **of** the **cycle** is important:
		- **Europe** & **Asia** - 220 to 240 volts of AC (VAC), 50 Hz
		- **US/Canada** - 110 to 120 VAC, 60 Hz
	- Typically **represented by** a **wave/curvy line**
- **Direct Current (DC)** = **Current** that **moves in one direction with** a **constant voltage**
	- Typically **represented by** a **solid straight line** with **dotted lines underneath**
 ![[Pasted image 20260908154126.png|227]]

### Dual-voltage Input Options
- **Voltage varies by country**, as such **so do the power supplies used**
	- Europe - 230 VAC, 50 Hz Power supply
	- US/Canada - 120 VAC, 60 Hz Power Supply
- **Some power supplies have** a **switch that allows** the **input type to be switched manually between 120V and 230V**
	- **Outlet** should be **tested with multi-meter** if unsure what **type of AC** is being **used**
	- Most modern power supplies can detect and automatically adjust accordingly regardless of country <- Called **dual-voltage** or **voltage-sensing**
- **Don't plug 120V power supply into 230V power source**
	- Can cause failure or fire
- Plugging 230V device into 120V outlet will fail to power it on

### Power Supply Output
- Provides **different voltages in DC for different components**
- Typically referenced as **positive and negative values**
	- **Voltage** = Difference in electrical potential between two points
		- e.g. At the front door of a house, second floor is +10 feet, basement is -10 feet
		- **Electrical ground** is a **common reference point**
		- Depends on where measurement is from
- **Rail** Refers to **wire or circuit providing** a **specific voltage level**
	- **Common rails** are, +12V, +5V, +3.3V
- **+12V**:
	- PCIe adaptors, hard drive motors, cooling fans, most modern components
- **+5V**:
	- Some components on the motherboard itself
		- Many components now using **+3.3V**
- **+3.3V**:
	- M.2 slots, RAM slots, motherboard logic circuits
- **+5 VSB**:
	- Standby Voltage <- Power provided to motherboard when in a standby/sleeping state so can be woken up via signals across a network or pushing a button on the case
- **-12V**:
	- Integrated LAN connections on a motherboard
	- Older serial ports
	- Some PCI cards
- **-5V**:
	- Used for older ISA adaptor cards
	- Most cards didn't use it
	- Modern motherboards don't have ISA slots

### 24-pin Motherboard
- **Main motherboard power**
	- Provides **+3.3V**, **+/- 5V**, and **+/- 12V**
- **Originally ATX standard** was a **20-pin connector**
	- **24-pin added for PCI Express Power**
- **24-pin connector can connect to 20-pin** motherboard
	- Some cables are 20-pin + 4-pin

### Redundant Power Supplies
- Using **two** (or more) **power supplies**
	- Often used for servers and other infrastructure devices
- **Each power supply can handle 100% of the load**
	- Normally run at 50% of the load
	- One can fail without shutting down the system
- Uses a **backplane** to switch between power sources as needed
- Designed to be **hot-swappable**
	- Allows faulty **power supplies** to be **replaced without powering down** the **system**

### Power Supply Connectors
- **Many** power supplies **have fixed connectors**
	- Connected to the power supply permanently
	- **May have too many connectors**, leaving some cables just sitting inside of the case
	- **May not have enough connectors**
- **Higher-end** power supplies **tend to be modular**
	- **Cables** can be **added as needed without leftover cables in** the **case** <- allows for **better airflow**
	- More expensive

### Sizing A Power Supply
- **Power Supplies rated by watts**
- **Higher wattage** power supplies often **more expensive**
	- Higher wattage than needed doesn't speed up a computer
- **Physical size tends to be standard**
	- Older cases and systems may have proprietary sizes
- **Calculate total watts needed for all components** before choosing power supply
	- CPU, Storage devices, video adaptor, etc.
- Separate Video Adaptors (e.g. GPU) usually the largest power draw
	- Many video card specifications list a recommended power supply wattage
- **50% capacity rule** = Power Supply can support 50% of total load today
	- Power supply runs efficiently and there's room to grow

### Energy Efficiency
- **Some power often lost when converting from AC to DC**
	- **Lost power converted to heat**
- Different efficiency ranges for power supplies
	- **Often** range **between 80% to 96%**
	- Can depend on voltage and redundant power
- **More efficiency = More DC power & less heat**
	- Saves money in powering computer as well as keeping computer cool
- Established certification program for power supplies to determine efficiency
	- 80 plus, 80 plus Bronze, 80 plus Silver, 80 plus Gold, 80 plus Platinum, 80 plus Titanium
- High efficiency Power Supplies reduces operational costs over time