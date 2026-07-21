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
- Deliver contents from its root directory, defined in the software settings
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