**Car Park**


**The Client-Server Process**
-  **Client** - The device or software sending the request to a server
- **Server** - The device or software that handles client requests and returns responses
- **Protocol** - Defines how a client can communicate with a server including:
	- The commands which both the client and server understand
	- How requests are structured
	- The syntax used
	- What response should be given to each request
	- What response to give to faulty requests
- **Port** - identifies a specific service running on a system (the port the server is "**listening**" on for that particular service)
	- Client must connect via the correct port when trying to access service on server
	- Allows one server to run multiple services without clashing or mixing up requests and responses
- **DNS** - Resolves website name to an IP address so correct web server can be found

**Web Communication**
- **HTTP(S)** = Stateless client-server protocol used for World Wide Web
	- Statefulness can be added to web apps at the application level through the use of session identifiers, usually stored in a token or cookie.
		- Web server can be programmed to create a session identifier once a user logs in with their credentials and each subsequent request sends a new one. Thus allowing the server to "remember" user settings or credentials
- HTTP specifications (the RFC/Request For Comments docs) list 9 core methods: ^a65b59
	- **GET** - Retrieves a resource from a web server
	- **POST** - Submits data to a web server and creates a new resource
	- **PUT** - Replaces an existing resource in its entirety or creates one if it doesn't exist on a web server
	- **DELETE** - Removes a specified resource from a web server
	- **PATCH** - Applies partial modifications to a resource, only affecting the fields specified by a client
	- **HEAD** - Similar to GET but only retrieves headers without the body
	- **OPTIONS** - Returns the communication options (allowed methods) for a resource
	- **CONNECT** - Establishes a raw TCP tunnel through a proxy to a destination server, typically for HTTPS traffic.
		- Doesn't encrypt data, only opens raw TCP connection to target host, dev must implement TLS/SSL (Transport Layer Security) for encryption to occur
		- Not to be confused with VPN Tunnel
	- **TRACE** - Echoes received request back to client for diagnostic purposes

- When viewing HTTP requests and responses through the network tab of the terminal - Filename: "/" means index.html
- Details of a HTTP request can be viewed by clicking on a request entry
- List of the HTTP response(s) can be viewed by clicking on a specific request and then clicking the response tab