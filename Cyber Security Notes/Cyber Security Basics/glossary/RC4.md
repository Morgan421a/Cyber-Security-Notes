- **Rivest Cipher 4 (RC4)**
	- A stream cipher that encrypts messages one byte at a time via an algorithm
		1. Secret key and text to be protected are input
		2. Cipher scrambles the text via encryption <- byte to byte instead of chunks
		3. Scrambled text forwarded to recipient <- Recipient should have a copy of the secret key used to encrypt the data
		4. Recipient reverses steps to decrypt data back to original text