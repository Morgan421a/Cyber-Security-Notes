**Car Park**

**ASCII**
- **Encoding** = The agreed upon way in which characters of a language are mapped to bits on a computer
- An early character encoding from 1963
- Uses numbers 0-127 to represent English letters, digits, punctuation and some control characters
- One of the earliest ways used to map characters to different streams of bits such that a letter or symbol is shown instead of just the bits
- Letters sit in order so knowing the hexadecimal or decimal for b (lowercase) allows someone to workout the decimal for a - z (lowercase)
- When using ASCII encoding, computer reads 42 in a file and displays `A` on the screen; when it reads 42 it display `B` and so on.
- Each character has it's own ASCII, including symbols such as `[` (hexadecimal 5B) 

- **ISO-8859-1 (Latin 1)** - Similar to ASCII but covered Western European languages such as German, French, Spanish, Italian, Portuguese, Catalan and Nordic Languages 
	- ASCII not usable here due to its 127/128 character limit it couldn't cover all letters of their alphabets
- **ISO-8859-2 (Latin 2)** - Supported Central/Eastern European languages such as Polish, Czech, Hungarian, Croatian, Romanian and Slovak
	- Same as previous, more characters = ASCII too limited for these languages

-  ASCII tried covering for the many different languages through the creation of regional variants (ISO's, Windows-1252, etc.)
	- This made sending and receiving data more difficult 
	- Both users had to know what encoding method was being used and match each other, else the data would be interpreted by the computer as different characters than intended by the sender

**Unicode**
- Universal character encoding standard
- Assigns unique code points to characters from all modern and historical writing systems globally. e.g.:
	- U+0041 = Latin A
	- U+03A9 = Greek "Ω"
	- U+3042 = Japanese Hiragana "あ"
- Supports the interchange, processing, and display of text in diverse languages
- Makes switching languages for a file or message easy
- Removes need to know/worry about what encoding is used by the original author since they'll also be using Unicode
- **Current version** = Unicode 17.0 defining close to 157,000 (*159,801 exactly*) characters, almost 4,000 of which being emoji sequences
	- *Set to move to Unicode 18.0 around September 2026. Adding around 14,047 new character meaning new total be over 172,000*

- **UTF = Unicode Transformation Format**
	- Standardised method for encoding Unicode characters into unique, reversible byte sequences for storage and transmission.
	- The most prevalent formats are:
		- **UTF-8** -> Very common on the modern web, encodes Unicode points into 1-4 bytes dynamically (decides on number of bytes based on char complexity). 
			- ASCII characters (U+0000 to U+007F) use exactly 1 byte
				- Identical to original ASCII, ensuring seamless backwards compatibility.
			- Non-ASCII characters like Ω (U+03A9) use 2 bytes
			- Complex Scripts or emojis such as  🔥 (U+1F525) require 4 bytes.
			- UTF-8's flexibility allows for efficient coverage of the Unicode standard without wasting bytes
		- **UTF-16** -> Uses 2 or 4 bytes per character
			- Common characters (Latin, Cyrillic, Chinese Hanzi) fit in 2 bytes
			- Rarer characters like emojis or ancient scripts require a pair due to code point value being greater than U+FFFF (65,535)
				- pair = two 16-bit units totalling 4 bytes
			- Example: A is encoded as U+0041 whereas  🔥 needs two and it encoded as a pair, U+D83D U+DD25
		- **UTF-32** -> Every Unicode point uses exactly 4 bytes
			- Example: A is encoded as U+0000000041 and  🔥 is encoded as U+0001F525
			- Simplest Format but also the most wasteful

	- **Common UTF In Simple Terms:**
		- **UTF-8 -> 1-4 bytes, dynamic assignation to characters**
			- Best and most efficient for Latin Languages
			- 1 byte per character for ASCII range
			- Backwards compatibility with ASCII = most dominant encoding for the web, file systems and most modern software
		- **UTF-16 -> 2 or 4 bytes per character** 
			- More space-efficient for languages with many characters outside the Basic Multilingual Plane (BMP) or those frequently using characters requiring 2 bytes in UTF-16
				- i.e. many Asian scripts: Chinese, Japanese, Korean
			- Uses pairs for characters whose code point value is greater than U+FFFF (65,535)/are larger than a single 16-bit unit (2 bytes) 
				- i.e U+D83D U+DD25 for 🔥
			- Generally less efficient than UTF-8 for purely Latin text due to 2 byte minimum per character
		- **UTF-32 -> 4 bytes per character (Fixed-width encoding)**
			- Simplifies internal processing, ensures every code point is represented uniformly.
			- Most "open"/straightforward in terms of mapping
			- Most wasteful regarding storage and bandwidth, typically using 2-4 times more space than UTF-8 for common texts