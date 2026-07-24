- **DNS = Domain name system**. Used to resolve domain name to web server IP addy.
	- Allows users to remember domain names instead of IP addies
- **Domain name hierarchy** = The parts that come together to form a domain name in order of their importance.
	- **TLD = Top level domain**, furthest right of domain name i.e. .com, .edu, .gov
		- 5 main types, 2 being = gTLD (Generic TLD) & ccTLD (Country Code TLD)
	- **SLD = Second level domain**, directly left of TLD, i.e. google in google.com
		- Can use hyphens (-) but not at start,end or consecutively
		- char limit = 63 + TLD
	- **Subdomain** = Sits directly left of SLD i.e. jupiter.server in jupiter.server.tryhackme.com
		- Can have as many as desired as long as not exceeding domain name total char limit (**253**) and must be separated by dots (.)

- **DNS records** = Categories of data stored on web server for particular domain, common ones include:
	- **A record** - IPv4 addy
	- **AAAA record** - IPv6 addy
	- **CNAME record** - Name of domain current one is hosted on
	- **MX record** - List of servers with authority to receive mail on domain's behalf
	- **TXT record** - Plain text field for domain, often contains list of servers permitted to send and receive mail on behalf of domain or login credentials (site dependent)

- **DNS Process** = Process used to resolve client domain name request to corresponding web server for domain:
	1. Client request -> device checks local cache first for address
	2. No address in cache = request forwarded to recursive DNS server -> checks own local cache too
	3. Still no, request forwarded to root DNS server -> sends referral (IP addy) list of TLD servers back to recursive DNS server
	4. Recursive server iteratively checks each TLD server in received list until one locates requested domain's corresponding authoritative DNS server
	5. Request forwarded to authoritative DNS server -> Sends IP addy for requested domain's web server back to recursive DNS server
	6. Recursive server caches result data and forwards data back to client
	7. Client device able to communicate with requested domain's web server

- **HTTP(S) = HyperText Transfer Protocol (Secure)** = Protocol used to dictate how clients and web servers communicate
	- **HTTP** = not encrypted 
	- **HTTPS** = encrypted + lets user know they're communicating with actual web server and not spoofed host

- **URL = Uniform Resource Locator** = Used to provide information to web server such that it can direct users to the particular site/page it hosts or provide resources
	- Made up of multiple parts, not all mandatory for every website/page, dependent on its purpose, some just provide extra information:
		1. **Scheme** - Protocol being used for communication i.e. HTTP/HTTPS
		2. **User** - User login credentials
		3. **Host** - domain/IP identifying the server
		4.  **Port** - port used by client and web server to communicate
		5. **Path** - Path taken from index to access the web page
		6. **Query** **String** - Extra info sent to the path i.e `?id=1`
		7. **Fragment** - Jump to specific part of web page (if dev allowed) i.e. `#section2`


- **HTTP Request Headers** = Used to tell web server key information for request, some headers are:
	- **Host** - Domain name of desired site on web server
	- **Content-Length** - The length of content to be sent, allows server and client to check for missing data upon response
	- **Accept-encoding** - The compression method used by the browser for data transfer
	- **Cookie** - Any cached cookies the browser might have for the domain such as a user's login credentials
	- **User-Agent** - The browser and software version the client is using
	- **Referer** - Name of domain that brought the client to this one
	- Requests **end with blank line** to let server know that request is finished


- **HTTP Response Headers** = Used by web server to tell client important information or instruct them on specific things such as what data to cache, some headers are:
	- **Server** - Software and version used by the web server
	- **Date**- Date, time and timezone in server's location
	- **Content-Length** - How much content should be received, allows client to tell if data missing
	- **Content-Type** - Type of content sent to client
	- **Content-Encoding** - Method used to compress data, chosen based on accept-encoding header's data from request
	- **Cache-Control** - How long cached data should be stored on client before it expires
	- **Set-Cookie** - Tells client what data to store as cookies in its cache
	- Responses **end with blank line** to let client know that response is finished
	- Anything after blank line = requested content/data

- **HTTP methods** = Commands used when making an **HTTP request** to web server, 9 common ones are:
	- **GET** - Requests data from server
	- **PUT** - Overwrites all of an existing record's data on web server (full mod) or creates new record
	- **POST** - Creates new record on web server
	- **PATCH** - Updates only specified fields of existing record on web server (partial mod)
	- **DELETE** - Removes specified records from web server
	- **TRACE** - Echoes requests back to client, used for diagnostic analysis
	- **CONNECT** - Creates connection tunnel between client and web server, not encrypted by default (not similar to VPN tunnel)
	- **HEAD** - Similar to GET but only returns headers without their body
	- **OPTIONS** - Lists available request methods for resource on web server

- **HTTP responses** will contain status codes informing the client of the result of their request, they tend to fall into groups, most notable being:
	- **1xx** - Information response, send next request -> **No longer very common**
	- **2xx** - Request successful
	- **3xx** - Request redirected
	- **4xx** - Client error
	- **5xx** - Server error

- **Cookies** = pieces of data stored on browser cache, collected when visiting different sites where set-cookie header is present in web server's response.
	- Allows client to store cached data, sent with each request under cookie header to allow web server to "remember" client i.e. login credentials where a "remember me" box was checked upon login (stored as a token = string of characters hard for humans to read/guess)

- **HTML** = Used to define the **language** **and** **structure** of web page using **elements** to define the parts/objects and **tags** to style them or provide metadata to enable JavaScript or CSS to manipulate specific elements.
	- Should always start with `<!DOCTYPE html>` to define the version of HTML browsers should use to interpret web page data
	- `<html> </html>` should come under aforementioned element and wrap all other elements inside it
	- `<head> </head>` Used to add/define data that isn't intended to appear on web page (can still be seen via source code) such as `<title> </title>` to add web page title in browser tab
	- `<body> </body>` wrapped by head element, all main page content placed within such as `<img>`(<- void element, no need to add closing tag), `<p> </p>` etc.

- **JavaScript (JS)** = Used to **add functionality and interactivity** to a web page on the **client-side**
	- Can be used to alter elements of web page on certain events such as clicking a button or hovering mouse over an element
	- Can be added directly to HTML file or loaded remotely from another file, both done using the `<script> </script>` element.

- **Cascading Style Sheets (CSS)** - Used to **style** elements of web page and make it look nice/modern

- **Sensitive data exposure** -> Occurs when sensitive info/data is left in frontend code of web page such as admin login credentials, links to hidden or private pages etc.
	- Sensitive data should be kept out of frontend or frontend should be checked through thoroughly prior to giving users access to web page
	- Data exposure can give attackers further access to other parts of a website where more damage can be done or more sensitive data is stored such as user information

- **HTML injection** = Failure to **sanitise** user input leading to them injecting **malicious HTML/JS code** to a web page through an input field (like a login box), allowing them to alter it or even gain access to parts of the website they shouldn't be able to.
	- All user input should be viewed as potentially malicious until sanitised
	- One way to sanitise user inputs is to remove any HTML tags prior to passing the data to the HTML code causing it to become nothing more than plain text.

- **Load Balancers** = **Software** used to spread client request traffic across multiple servers by selecting which server is currently best suited to deal with a request. 
	- Achieved through the use of algorithms, two of which being:
		- **Round-Robin** = Passing requests to each server in turn, like an infinite queue
		- **Weighted** = Checks which server is currently least bust and sends in request there

	- Also carry out periodic **Health Checks** to ensure servers are up and running correctly by sending its own request to them 
		- If a server does not respond at all or responds in an unexpected way, load balancer stops sending requests to that server until it responds as expected again.

- **Static content** = Content that is unchanging regardless of the client/user or time it was requested, such as image/JavaScript files, copies are stored on edge servers while origin servers store the original in the context of CDN
- **Dynamic content** = Content that can change depending on the client/user or the time at which it's requested, such as results from a user's search on a website, stored on the origin server only in the context of CDN

- **CDN = Content Delivery Network** = Using Edge servers and Origin servers to store both static and dynamic content for a website to quickly send it to users upon request.
	- **Edge servers** = Placed around many geographic locations, store only copies of a website's static content on their cache to send to clients upon request.
	- **Origin servers** = Fewer in number but store the original version of the static content as well as the dynamic content, both of which it forwards to the edge servers as and when it is requested.
	- CDN finds which edge server is closest to client and forwards requests there to increase speed of content delivery, helping to reduce traffic and improve user experience
	- Origin server never communicates directly to client, only to the edge server
	- **VPN** will alter perceived closest edge server potentially slowing content delivery speed due to need to jump between more servers when sending requests and responses

- **Databases** = Dedicated servers designed to store client data through the use of software to allow for interaction and retrieval of said data.
	- Interacted with via backend code to send requests to alter/retrieve data
	- Different database software available, each with different focuses, some include:
		- MySQL
		- MSSQL
		- MongoDB
		- Postgres

- **Web Application Firewall (WAF)** = **Software** that **exists between the client and the load balancer**, used to detect potentially malicious requests and drop them (silently) before they reach the web server.
	- Checks requests for common attack methods as well as if the request came from a bot or an actual user/client
	- Also checks for excessive requests over a period of time configured by the admin, helping to protect against things like DDoS attacks

- **Web Servers** = The physical servers upon which websites are hosted through the use of software, some examples of which being:
	- Nginx
	- Apache
	- IIS
	
	- Servers store content sent in responses in their root directory whose location can be configured during setup. Every server software has a default location for example:
		- Nginx and Apache root directory path is `/var/www/html` on linux OS's
		- IIS root directory path is `C:/inetpub/wwwroot` on windows OS's

- **Virtual Hosts** = Text based config files of all the domain addresses hosted on a server, allowing a single physical server to host multiple domains at the same time
	- If requested domain isn't found on a server it will respond with its default domain instead of the requested one, but this must be programmed into it, else it will just throw an error 404 (page not found)
	- No limit to the number of virtual hosts on a server at a time
	- Can have root directory mapped to different locations on the hard drive

- **Scripting and backend languages** = Used to **provide functionality** to a web page by adding interactivity for clients/users to **send/request/manipulate data** on the web page which can then be reflected via sending and receiving requests and responses to the web server and database.
	- Some languages for this include:
		- Python
		- Perl
		- Ruby
		- PHP
		- NodeJS

- **Full Web page request process:**
	1. Client makes a request to a web page
	2. DNS request process - finds domain's host server
	3. The three way handshake (goes through WAF and load balancer) - connects client to host server for communication via the same port i.e. 80 for HTTP or 443 for HTTPS
	4. Client's HTTP request is forwarded
	5. Client HTTP request is caught by WAF and checked for malicious or excessive requests as well as botting
	6. Client's HTTP request forwarded to load balancer which uses an algorithm to see which server is currently best suited to handle request
	7. Request is forwarded to web server which sends an HTTP response containing the data for the requested web page (assuming request was valid)
	8. Response containing web page data sent back to client and formatted by browser for client's use
