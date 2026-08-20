**Car Park**
- Why not use symbols as well as letters in encrypted data? 
	- **Modern encryption** operates on **raw bytes/binary data** instead of letters specifically; since everything is just binary at that level, **no letters-only limitation exists**
- DNS style system in place for public keys? <- so no need to remember a user's public key to send data to them 
	- **Yes**, but **no single universal system** - fragmented by use case:
		- **Certificates (PKI)** - automatic, trusted, verified (HTTPS/websites)
		- **PGP key servers** - public, searchable, but largely unverified/manual (personal encrypted email)
		- **Regular email** (Gmail <-> Outlook) **doesn't use public key** lookup at all - relies on **server-to-server trust + TLS**, not personal keys

#### **Why Cryptography Matters**
- Due to the way in which data travels to a target host, bouncing through dozens of routers and computers, anyone with access to those systems could read, change, or block the data.
	- **Cryptography** prevents this by using **mathematical rules** and **secret keys** to scramble data into gibberish that only **authorised people** can unscramble.

#### **Hiding Information - Symmetric Encryption**
- **Symmetric Encryption** - Entails both the sender and the recipient sharing the same private key to encrypt and decrypt the data
	- The same key **encrypts** and **decrypts** the message
	- Both sender and receiver need a copy of the key
	- The key must stay secret from everyone else
- **Symmetric encryption is**:
	- **Fast** - Can churn through huge amounts of data very quickly
	- **Efficient** - Perfect for encrypting files, hard drives and network traffic where speed matters
- Suffers from the **Key Distribution Problem** <- Solved by **Asymmetric Encryption**
	- How do the two users share the key safely over the internet?

- **Encryption Process**:
	- plaintext + encryption algorithm + key -> ciphertext
		- Real world encryption is more sophisticated but the basic pattern remains the same
- **Decryption Process**
	- ciphertext + decryption algorithm + key -> plaintext

- **Algorithms** can be and usually are **publicly known** and tested by experts globally 
	- The **security** comes from **keeping the keys secret**

- Ciphertext should look like gibberish to anyone who doesn't have the **key**

- **The Caesar Cipher** - Encryption technique whereby **each letter** in a message is **shifted** by a **fixed number of positions in the alphabet**. The **fixed number** is the **key** i.e. if key = 3, A -> D, B -> E, C -> F, and so on, upon reaching the end of the alphabet it wraps back to the start
	- Reportedly used by Julius Caesar over 2000 years ago to send military messages
	- **Not Secure** and **never used in real systems**:
		- Too easy to compromise and decrypt messages, especially for a computer
		- Can be brute forced by a person
- **Real Algorithms** such as **Advanced Encryption Standard (AES)** are vastly **more complex and secure** than the Caesar Cipher but both follow the same basic idea: algo + key + plaintext -> ciphertext

#### **Sharing Keys Safely: Asymmetric Encryption**
- **Asymmetric Encryption**:
	- Solves the **key distribution problem** by using two mathematically linked keys:
		- **A Public Key** - Anyone can know and use
		- **A Private Key** - Only one person keeps secret
		- If something is encrypted using someone's **public key**, only their **private key** can decrypt it
		- If something is encrypted using someone's **private key**, anyone with their **public key** can decrypt it. <- Primarily used for digital signatures
	- The two keys are connected via maths, ordinary computers would need hundreds or even thousands of years to recover the private key from the public key. 
		- This computational difficulty is what makes **asymmetric encryption** secure.

- **Real World Use: HTTPS**:
	- HTTPS = The most common everyday use of **asymmetric encryption** (shown in URL, sometimes padlock icon in the browser too)
		- `https://google.com` request process:
			1. Browser requests website's public key
			2. Website sends back its public key wrapped in a **certificate**
				- When a website hands over a **certificate**:
					- Browser checks a trusted CA signed it
					- Browser checks it's still valid (not expired or revoked)
					- If everything looks good, browser shows the padlock and trusts the public key
						- If something's wrong -> browser displays a warning and might refuse to connect
			3. Browser and website use **asymmetric encryption** to agree on a **symmetric key** without anyone else being able to see it
			4. From there on, they switch to symmetric encryption using the symmetric key for the rest of the session.
			- Sometimes called a **hybrid approach**:
				- **Asymmetric encryption** - Solves the key distribution problem
				- **Symmetric encryption** - Used once symmetric key agreed on both ends cause it's much faster
		- Can view HTTPS site certificate by clicking the padlock icon in the address bar, then "view certificate"

#### **Symmetric vs Asymmetric**
- In practice, Real systems use both (**hybrid approach**)
	- Asymmetric, initiates a connection and securely shares a symmetric key
	- Symmetric takes over for the remainder of the session to efficiently handle data
		- How HTTPS, VPNs and encrypted messaging apps all operate

|                    | **Symmetric**                                 | **Asymmetric**                                  |
| ------------------ | --------------------------------------------- | ----------------------------------------------- |
| **Number of keys** | One key for both encrypting and decrypting    | Two keys: Public and Private                    |
| **Key Sharing**    | Both users need the same key                  | Public key can be shared openly                 |
| **Speed**          | Very Fast                                     | Slower (Used for small amounts of data)         |
| **Main Use**       | Encrypting bulk data (files, network traffic) | Sharing keys, securely and digital certificates |
| **Analogy**        | One key locks and unlocks a box               | Mailbox: anyone posts, only the owner retrieves |

#### **Key Terminology**
- **Plaintext** - A message that **can be read normally** i.e. "Hello World!" or "Patient Name: John Smith"
- **Ciphertext** - A **scrambled** version of a message that's **not supposed to make sense** i.e. "KHOOR" or "Sdwlhqw qdph: Dolfh Vplwk"
- **Key** - Controls **how scrambling and unscrambling works**; effectively like a password the algorithm uses
- **Algorithm** - The **set of steps** that explain **how to use the key on the message**; everyone can know the algorithm, the **security** comes **from** keeping the **key secret**
- **Certificate** - Digital Document which: 
	- Contains someone's public key 
	- States who that key belongs to (i.e. example.com)
	- A trusted digital authority signs it, called a **Certificate Authority (CA)**

- **Certificate Authority (CA)** - Entity that stores, signs, and issues digital certificates
	- Browsers and Operating Systems come preloaded with a list of trusted CAs.