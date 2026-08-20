**Car Park**

**Representing Colours**
- Computers can show 8 colours using **bits**, it can turn on multiple colours and layer them to create colours it's unable to create directly, i.e. 000 (all colours off) = black, 111 (all colours on) = white, 101 (red and blue on) = magenta
	- Done using **binary** (1's and 0's)
	- **3 bit colours** have effectively been completely **replaced**, only seeing use in niche circumstances i.e. retro computing hobbyist communities
- Modern computers can use hexadecimal granting access to over 16 million colours through the use of 256 levels instead of just 3 (RGB). Done using a **byte** (**8 bits**) also known as an **Octet**
	- Still uses **binary** but each colour is represented as **3 bytes (24 bits)** instead of only **3 bits**
	- **Hexadecimal Representation** - Allows for single characters to act as **symbols** for a set of **4 bits (0000 - 1111)** ranging from **0-9 and A-F**, allowing for easier use of hexadecimal numbering systems. i.e. green can be shown as **A3EA2A** instead of its full hexadecimal number
	- **3 byte (24 bit)** colours have become the **dominant standard** for modern computing

**Decimal and Hexadecimal**
- **Decimal** = base-10 system (0-9)
	- Rightmost digit multiplied by $10^0$, next digit multiplied by $10^1$ and so on until leftmost digit is reached
- **Binary** = base-2 system (0-1) <- **1 bit**
	- Limited to two digits, 0 and 1, everything is a power of 2
		- e.g. 1001 in binary can be expressed as: 
			- 1 x $2^3$ + 0 x $2^2$ + 0 x $2^1$ + 1 x $2^0$ = 1 x 8 + 0 x 4 + 0 x  2 + 1 x 1 = 8 + 0 + 0 + 1 = 9
	- Rightmost digit multiplied by $2^0$, next digit multiplied by $2^1$ and so on until leftmost digit is reached

- Practice equations:
	- 1 * $2^3$ + 1 * $2^2$ + 0 * $2^1$ + 0 * $2^0$ = 12 = 1100 
	- 1 * $2^3$ + 1 * $2^2$ + 0 * $2^1$ + 1 * $2^0$ = 13 = 1101 
	- 1 * $2^3$ + 1 * $2^2$ + 1 * $2^1$ + 0 * $2^0$ = 14 = 1110 
	- 1 * $2^3$ + 1 * $2^2$ + 1 * $2^1$ + 1 * $2^0$ = 15 = 1111

		- **^ Exponents pattern, counts down for each column i.e. $2^7$, $2^6$, $2^5$. . . , $2^2$, $2^1$, $2^0$**
		- **Can also memorise sequence 1, 2, 4, 8, 16, 32, 64, 128** <- stops at 128 cause **8 bits** == **1 byte**
			- **represented by equations as 128, 64, 32, 16, 8, 4, 2, 1**

- **Binary** can go **infinitely** by adding more digits to the left

- **Hexadecimal** = base-16 (0-9 & A-F) <- groups **4 bits** per digit
	- 10, 11, 12, 13, 14, 15 **replaced by** A, B, C, D, E, F
	- For example: 
		- 9BDF = 9 x $16^3$ + 11 x $16^2$ + 13 x $16^1$ + 15 x $16^0$ = 9 x 4096 + 11 x 256 + 13 x 16 + 15 x 1 = 39,903
		- Same rule of exponents as in binary equations
		- **^ easier to split each bit into their separate binary numbers (4 digits), calculate the value of each bit then add the total of all bits together**

- **Octal** = base-8 system (0-7) <- Groups **3 bits** per digit <- **Less common** than binary or hexadecimal
	- For example:
		- 357 (octal number) = 3 x $8^2$ + 5 x $8^1$ + 7 x $8^0$ = 3 x 64 + 5 x 8 + 7 x 1 = 239 = 
			- 011 + 101 + 111 = 011101111 
		- octal 12 = decimal 

- **Quaternary** = base-4 system (0-3) <- Groups **2 bits** per digit <- **rarely used** in modern computing

- **Bit** - Short for **Binary Digit**, either 1 or 0

- **Byte** = On modern systems is **8 bits**, also called an **Octet**

#### **Computers don't do the maths they literally read the physical state of the numbers, 357 to humans is read as 3, 5, 7 to computers in separate groups of bits until put together i.e. 011101111 is all the computer sees (3 groups of bits) which adds up to 239 in decimal**
