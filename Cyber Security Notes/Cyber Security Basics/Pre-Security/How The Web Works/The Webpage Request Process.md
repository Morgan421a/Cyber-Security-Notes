**The Process**
1. User requests a website
2. Computer uses DNS to find the website server's IP address 
3. Uses HTTP protocol to make requests
4. Web server uses HTTP responses to return web site / web page elements i.e HTML, JS, CSS, Images, Videos etc
5. Browser formats the received elements correctly and shows them to the User

**Load Balancers**
- Helps high traffic websites handle the load
- Provides a failover if a server becomes unresponsive
- If request is made to website with load balancer:
	- LB receives request first and forwards it to one of the servers behind it
	- Uses algorithms to decide which server is currently best to handle the request.
	- Some example algorithms are:
		- **Round-Robin** - Sends request to each server in turn
		- **Weighted** - Checks which server is currently the least busy and sends the request to that one
- Perform periodic **health checks** to ensure a server is running properly, if server doesn't respond appropriately or at all, LB stops sending traffic until it responds appropriately again.

**Content Delivery Network**
- Uses Edge Servers to serve static content (HTML, JS, CSS, images, videos, etc) from its cache to users geographically closest to them
- When a user requests a hosted file, CDN works out which Edge Server is physically closest to them and sends the request there
- Helps reduce traffic to a busy website and makes user experience better through faster content delivery
- Stateless regarding user data such as login details/states and DB records but Stateful regarding connections to the origin server (client - edge server = stateless, edge server - origin server = stateful, client - origin server = non-existent since no direct communication)
- Only stores static content, in the event that the user requests dynamic content, the Edge Server passes the request to the Origin Server (main server) who then sends the data back to the Edge Server first so it may be forwarded to the client.
- VPNs will change the Client's perceived closest Edge Server and will send the request there from which the data is passed back through the VPN servers (can strip away the encryption and see where the request originated from) and Edge Servers using the OSI Model to deliver the data to the client.
	- Edge Servers will view the VPN server *as* the user
	- Often increases the load times for the website


**Databases**
- A way for websites to store information for users
- Web servers can communicate with DBs to store and recall data from them
- Can be just a plain text file up to a much more complex cluster of multiple servers to provide speed and resilience
- Some common DBs are:
	- MySQL
	- MSSQL
	- MongoDB
	- Postgres
- Each have specific features


**Web Application Firewall (WAF)**
- Sits between web requests and web server
- Primary purpose = Protect web server from hacking or DDoS attacks
- Analyses web requests to check for common attack techniques, whether the request is from a real browser instead of a bot.
- Also check for excessive number of requests via rate limiting which only allows a certain amount of requests within a configured period of time
- If it deems a request as a potential attack it drops it so it never gets sent to the web server


**How Web Servers Work**
- Web Server = Software which listens for incoming connections and responds using HTTP protocol to deliver web content to clients.
- Some common web servers are:
	- Apache
	- Nginx
	- IIS
	- NodeJS (*Technically a JS Runtime that **can** act as a web server but is typically considered an application server in enterprise architectures*)
- Deliver contents from its [[Root Directory]], defined in the software settings
	- e.g. Nginx & Apache both have the default location of /var/www/html on linux OS's
	- IIS uses C:\inetpub\wwwroot for windows OS's

**Virtual Hosts**
- Text-Based Config Files used by Web servers to host multiple websites under different domain names
- Server software checks requested hostname from HTTP headers and matches it against its virtual hosts 
	- If match found, provides the correct website
	- If no match found, provides the default website instead (*Must be programmed in, not inherent else will throw error 404*)
- Can have root directory mapped to different locations on the hard drive e.g:
	- [one.com(opens in new tab)](http://one.com/) being mapped to /var/www/website_one
	- [two.com(opens in new tab)](http://two.com/) being mapped to /var/www/website_two
- No limit to number of websites a web server can host

**Static Vs Dynamic Content**
- Static content = content that never changes i.e. images, JS, CSS, etc
	- Can also include HTML that never changes
	- Files are directly served from web server with no changes made to them
	- Usually cached by the server if it's an edge server
- Dynamic content = content that can change with different requests such as a search function giving differing results depending on the field's input. 
	- Typically served from a main/origin server, especially in the case of CDNs
	- Changes caused by backend logic via programming and scripting languages

**Scripting and Backend Languages**
- Used to make a website interactive to a user
- Can interact with DBs, call external services, process data from user, etc
- Some example languages are:
	- Python
	- PHP
	- Ruby
	- NodeJS
	- Perl
- Adding interactivity can open up many **security issues** for web applications which need to be properly covered prior to public use

**Full Website Request Process**
1. User requests a website
2. Device Checks local cache for website IP address
3. Not found in local device cache so device checks recursive DNS server for the address
4. Recursive server queries root server to find correct authoritative DNS Server
5. Authoritative DNS server advises the IP address for the website
6. Web Application firewall checks request for signs off hacking/attack attemtps based on configuration
7. Request passes through  load balancer which uses algorithms to find server currently best suited to handle request
8. User device connects to web server on port 80 or 443 unless configured otherwise by developer
9. Web server receives HTTP GET request
10. Web application talks to database to retrieve website data and sends said data back to user device
11. Browser renders data into a viewable (and interact-able if possible) website

## **Summary**
- Web page request process:
	1. User/Client makes a request for a web page
	2. their local cache is checked for the page
	3. if not there, request is forwarded to recursive DNS server who checks its own local cache
	4. if still no, recursive server sends the request to the root DNS server who sends a referral list (list of IPs)  of the TLD servers to query for the request to the recursive server
	5. Recursive server iterates through each TLD server on the referral list until one responds
	6. TLD server forwards the request to the authoritative DNS server
	7. Authoritative server sends the address for the web server back to the recursive server that then caches the response data and forwards the request back to the client
	8. The Three-Way handshake (TWH) occurs (including Load balancers and WAF)
		- **TLS handshake** occurs after the TWH only if the site uses HTTPS
	9. Client's HTTP request is sent to the web server via the browser (can be an API or microservice in the event of a non-user/automated client)
	 10. Web Application Firewall (WAF) checks the request against its own rules by checking the contents of the request for common attack methods as well as if the client is not a bot. If the request is flagged as malicious it is dropped (silently) before it ever makes it to the web server
		- Also checks for excessive number of requests within a configured space of time
	11. Load balancer uses its algorithms to see which server is best suited to handle the request:
		- Round-Robin = requests sent to each server in turn, like an infinitely looping queue
		- Weighted = Checks which server is the least busy and forwards the request there
	12. Web Server receives the request and, if valid, sends a response back to the client with the requested data
	13. Client's browser processes data to produce the web page as intended by the developer

- Load Balancers = Software that uses algorithms to help spread incoming traffic (requests) across multiple servers. Done through the use of algorithms, a couple of which being:
	- Round-Robin = Passes requests to each server in turn, similar to how a queue works but this one loops infinitely (unless something goes wrong)
	- Weighted = Checks which server is currently the least busy and sends the request there

- Web Application Firewall (WAF) = Software that exists before the load balancer and the web server (most commonly before but can come after load balancer). 
	- Analyses client requests for common attack methods as well as if the request came from a bot
	- Also checks for an excessive number of requests over a configured period of time (protects from things like DDoS)
	- If any of the aforementioned scenarios are flagged the WAF drops (silently) the request such that the web server never sees it

- Web Servers = Dedicated hardware upon which web sites are hosted.
	- Use software to control and handle the infrastructure of the web applications on them, some of the most popular are:
		- Apache
		- Nginx
		- IIS
		- Node JS <- *Not really used for that in the real world despite being possible, more so used for application servers*
	- Files are stored on the root directory of the web server, which is where the files/data are sent from to fulfil client requests.
		- Different web server software use different default locations i.e.
			- Apache and Nginx both default to: `/var/www/html` on linux Operating Systems <- Had to check notes
			- IIS defaults to `c:/inetpub/wwwroot` on Windows Operating Systems <- Had to check notes
		- Root file location is configured in the system settings

- Virtual Hosts = Allow multiple web servers to be run on the same physical server without conflicting with each other or mixing up requests. 
	- Done by using text-based config files to list the addresses of each web server stored on the same server (listed as the website domain names) <- had to check notes
	- Server software checks Host header in user request and matches it to the correct virtual host: <- had to check notes
		- If match found sends the correct website
		- If no match found sends the user the server's default website instead (must be programmed in else error 404) <- had to check notes
	- No limit to the number of websites a server can host <- had to check notes
	- Root directory can be mapped to different locations on the hard drive <- had to check notes

- Content Delivery Networks (CDN) = The use of edge servers and origin servers to send static and dynamic content, respectively, to users.
	- Edge servers = Many smaller servers in a lot of different geographic locations, keeps static site content on its cache for quick retrieval and delivery.
	- Origin Server = Larger servers in fewer numbers, stores all of the content for a website (static and dynamic), never communicates with client directly unlike edge servers. 
	- When cached content is needed the edge server forwards a client's request to the origin server then forwards the response back to the client
- When client requests content the CDN checks which edge server is closest to them and forwards the request there. 
	- Allows for faster response times and thus a better user experience

- Databases = Software designed to store data for a server or application.
	- There are different types each with their own main focus, some include:
		- MySQL
		- MongoDB
		- Postgres
		- MSSQL
	- Upon request a web server retrieves necessary data from the DBs to send back to the user as well as forwarding requests to update, add or delete data

- Static vs Dynamic content:
	- Static = Content that is unchanging such as images or CSS
	- Dynamic = Content that changes based on the client or when the data is requested such as a search bar or a user's stored data

- Scripting and Backend Languages  = Languages used to make a website interactive as well communicate with web servers, databases or call external services  <- Had to check notes, defined them as general not specifically to websites
	- Some examples include:
	- Python
	- Java <- *Added from later notes*
	- Perl
	- Ruby
	- PHP <- had to check notes
	- NodeJS <- had to check notes