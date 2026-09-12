### CPU Architecture
- **CPU** = Central Processing Unit
	- Referred to as the **Processor**
	- **Executes program code** in **software** **or** **firmware**
	- Performs basic operations for instructions
- **Cache** = High speed memory inside the processor
#### CPU Operation
1. **Fetches** the next **instruction** **from** system **memory** (e.g. RAM) **or** **processor cache**
2. **Decodes** the **instruction** **through** the **control unit**
3. **Executes** the **instruction** **or** **passes** it **to** a **secondary unit** for completion
	- Secondary unit = a co-processor such as a GPU
4. **Sends result to** the **register**, **cache**, **or** **memory** for storage or further use

### Operating System Technologies
- **32-bit** and **64-bit**:
	- The **capabilities of a processor** <- How much information it can process at a time
	- The **total amount of address space** a **CPU can reference**
	- **Hardware Drivers** are **specific** **to** the **OS version** (32-bit/64-bit)
#### 32-bit
-  **32-bit** processor can store 1's and 0's **up to $2^{32}$ = 4,294,967,296 values** <- Number of different binary patterns
- **32-bit** usually **referenced as** an **x86** processor
- **32-bit** processor **can reference** **4 GB** of **memory**
- **32-bit** OS **can't run 64-bit apps**
	- **x86** processors **limited to 32-bit operations** and **4 GB** of **RAM**
#### 64-bit
- **64-bit** processor can store 1's and 0's **up to $2^{64}$ = 18,446,744,073,709,551,616 values** <- Number of different binary patterns
-  **64-bit** usually **referenced as** an **x64** processor
- **64-bit** processor **can reference 17 billion GB** of **memory** <- Possible but **limited by Operating Systems' maximum supported values**
- **64-bit OS can** usually **run 32-bit apps**
	- **x64** processors can **support both 32-bit and 64-bit operations** and **higher memory capacities**
- **Apps in** a **64-bit Windows OS**
	- **Programs folder** has **different areas for apps** **depending on** the **type** of apps that are **installed**:
		- **32-bit** apps: `\Program Files (x86)`
		- **64-bit** apps: `\Program Files`
#### Advanced RISC Machine (ARM)
- CPU architecture developed by Arm Ltd.
	- Design the chip and license the specification to third parties
- Tend to use a **simplified instruction set** <- **RISC** = Reduced Instruction Set Computer
	- Uses **less power**
	- Generates **less heat**
	- Allows for **fast and efficient processing**
	- **Smaller instruction set compared to x86 and x64**
- Traditionally used for mobile and IoT devices
	- Designed for low-power devices
	- Adoption by Apple and other manufacturers for desktops and laptops
		- e.g. Chromebooks and Android Systems

### Processor Core
- CPUs may be referenced by the **number of cores** they have:
	- Dual-Core (2-Core)
	- Quad-Core (4-Core)
	- Octa-Core (8-Core)
	- Multi-Core (More than one core/not a uniprocessor (single-core))
- Number of cores increasing as new generations developed
- **Each core** typically **has** an **individual CPU and cache** (CPU -> L1 Cache -> L2 cache (if it has one)) <- **Layout horizontal** (planar layout) **not vertical**, **cores and caches sit side-by-side**
	- Allows **multiple cores** to **perform multiple instructions** **simultaneously**, thus **increasing** the **computing efficiency**
	- **Some chips** may **have** a **shared cache**