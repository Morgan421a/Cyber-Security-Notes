##### **Net-NTLM Authentication**
- Uses a **Challenge-Response** mechanism as such:
	1. Client sends authentication request to the desired server
	2. Server generates random number and sends it as a **challenge** to the client
	3. Client combines their NTLM password hash with the **challenge** (and other known data) to generate a **response** to the challenge and sends it back to the server for verification
	4. Server forwards the **challenge** and the **response** to the **Domain Controller (DC)** for verification
	5. **DC** uses the **challenge** to recalculate the **response** and **compares** it to the original **response** sent by the client; if both match, client is authenticated, otherwise client is denied. **Authentication result sent back to the server**
	6. Server Forwards authentication result to the client
- Users **Password** (or **hash**) is **never transmitted** through the network for security
- Above process **only applies** when using a **domain account**
	- If local account used, server can verify response to challenge **without** needing to interact with the **DC** since it has the **password hash stored locally** on its **Security Account Manager (SAM)**
