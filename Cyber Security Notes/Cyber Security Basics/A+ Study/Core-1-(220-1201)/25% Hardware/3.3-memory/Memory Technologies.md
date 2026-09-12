### Memory That Checks itself
- Used on critical computer systems (e.g. VM servers, db servers, any server)
- **Parity Memory**:
	- Includes an **additional Parity Bit** with each byte stored in the memory<- bit used to detect an error
	- Looks at a byte of data (8 bits) and essentially **adds** a **9th bit**, called a **parity bit**, to the byte 
		- Most systems use **even parity**, where extra bit makes **all 9 bits add up to an even number** (e.g. 11100111 total already even (totals to 6) so parity bit = 0, therefore 111001110)
	- Byte evaluated with parity check when retrieved from memory, if parity bits are identical then byte assumedly intact and there are no errors present, otherwise some form of error must have occurred
	- **Won't always detect** an **error**
	- **Can't correct** an **error**
- **Error Correction Code (ECC) Memory**:
	- **Detects** **errors** **and** **corrects** on the fly
	- Not used in all systems
	- Looks the same as non-ECC memory

### CPU to RAM Throughput
- **Memory Bandwidth** = Maximum throughput between RAM and CPU
	- Measured in MT/s (Megatransfers/s) <- Million transfers per second
		- e.g. 32 GB DDR5, 1 x 32GB, 5600 MT/s
- Faster is better <- Physics becomes the challenge in increasing speed

### Multi-Channel Memory
- Difficult to increase the speed of memory
- Adding **more channels between CPU and memory** allows **CPU** to **communicate** with **multiple** memory modules** at the **same time**, **increasing** overall **throughput** of a system
	- Two independent **memory buses** doubles the throughput
- Different motherboards have varying memory slots (e.g. Ram slots)
	- Single-Channel (64-bit bus) ,Dual-channel (128-bit combined total), triple-channel (192-bit combined total), or quad-channel (256-bit combined total)
	- Memory module slots often coloured differently
- Memory combinations should match
	- Exact matches are best
