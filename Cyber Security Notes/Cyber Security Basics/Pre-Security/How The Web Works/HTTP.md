**Car Park**
- DDoS attacks cause error 503 for other clients requesting the resource? = Yes they are one of the possible reasons for the error occurring, often done by the server or its protective firewall/CDN rejecting new requests intentionally as a way of preventing a total system crash

**What is HTTP?**
- **HTTP**
	- Set of rules used for communicating with web servers and for web page data transmission
	- Developed by Tim-Berners Lee and his team between 1989 and 1991
	- Stateless - Doesn't keep track of previous client requests
- **HTTPS**
	- Secure version of HTTP
	- Encrypts data to prevent others from seeing said data during transmission (sent or received)
	- Also gives the user assurance that they're communicating with the correct web server and not an impersonator
	- HTTP + SSL/TLS (Transport Layer Security) -> HTTPS
		- Without ^ these the connection can never be HTTPS

**Requests and Responses**
- URL = Usually a set of instructions on how to access a resource on the internet
	- Has many features that can be added or omitted depending on the needs of the client or the function of the website
	- Features are in order as follows:
		- Scheme - What protocol to use for accessing the resource (HTTP, HTTPS, FTP)
		- User - Used for services that require authentication, username and pw can be entered in the URL to log in
		- Host - Domain name or IP addy of desired server
		- Port - Port to connect to, typically 80 or 443 for HTTP or HTTPS respectively but can be hosted on any port between 1 - 65535
		- Path - The file name or location of the resource to access
		- Query String - Extra information that can be sent to requested path. i.e. /blog?id=1 would request blog path to send blog article with id of 1
		- Fragment - Reference to a location on requested page itself. Typically used for pages with long content and can have specific parts of page directly linked to it. Makes it viewable to clients as soon as they access page

- Possible to make HTTP request with one line **GET/HTTP/1.1**
	- Better to send more information through **headers** which contain extra information for the web server the client is communicating with, some common headers include:
		- Host - The domain name or IP addy of the desired web server, if omitted web server will just send its default website
		- User-Agent - Allows a client to identify its software type (e.g browser), version, OS and device to the web server to enable tailored responses
		- Content-Length - Tells web server how much data to expect so it can ensure none is missing, used when client is sending data to web server such as in a form
		- Accept-Encoding - Browser's supported compression methods so web server knows how to compress data appropriately for transmitting over the internet
		- Cookie - Data sent to server so it can remember client information
		- Referer - The web page that referred the client to the requested one
		- HTTP Requests end with blank line to inform web server that request has finished
- Upon request a HTTP response is sent back to the client, usually starts with:
	- HTTP/1.1 200 OK - Protocol version used by the web server, status code "200 OK" tells client the request has completed
- Responses also use headers similar to the request, some common response headers are:
	- Server - The web server and software version number
	- Date - The current date, time and timezone of web server
	- Content-Type - The type of information that will be sent i.e. HTML, images, video, PDF, XML, allowing browser to know how to process the data 
	- Content-Length - Tells client how long response is so they can confirm there is no data missing
	- Set-Cookie - Information to store which gets sent back to web server on each request
	- Cache-Control - How long contents of a response are to be stored in browser's cache before it requests again
	- Content-Encoding - The method used to compress the data for transmission
	- Blank line to confirm end of HTTP response
	- Anything after is the requested information

**HTTP(S) Methods**
- HTTP Methods = ways for client to show what actions they want to do when making  HTTP request. Most common ones are:
	- GET - Get info from web server
	- POST - Submit data to web server and potentially creating new records
	- PUT - Submit data to a web server to update existing information
	- DELETE - Deleting info/records from web server
	- ^ Basic 4 methods, click link for[[Client-Server Basics#^a65b59 | the core 9]]

**HTTP Status codes**
- Always used in first line of HTTP response to tell client of request outcome and potentially how to handle it. 
- Can be broken down into 5 ranges:
	- 100 - 199 -> Information response = Tells client first part of request was accepted and rest of request should continue to be sent. **No longer very common**
	- 200 - 299 -> Success = Tells client request was successful
	- 300 - 399 -> Redirection = Redirects client's request to another resource. Can be a different web page or entirely different website
	- 400 - 499 -> Client Errors = Inform client of an error with their request
	- 500 - 599 -> Server Errors - Reserved for errors occurring server-side, tend to indicate a major issue with the server handling the request

- Applications can define their own HTTP status codes
- Lots of different status codes, most common ones include:
	- 200 - OK = Request completed successfully
	- 201 - Created = Resource has been created i.e. a new user
	- 301 - Moved Permanently = Redirects client's browser to a new web page or tells search engines the page has moved elsewhere and to look there instead
	- 302 - Found = Similar to 301 but change is only temporary and may change again in future
	- 400 - Bad Request = Something wrong or missing from browser's request, sometimes used if requested web server resource expected certain parameters that client didn't send
	- 401 - Not Authorised = Currently not allowed to view resource until authorised with web app, usually with username and pw
	- 403 - Forbidden = No permission to view resource even if logged in
	- [[405]] - Method Not Allowed = Request method invalid for resource i.e. a GET request to /create-account when a POST request was expected
	- 404 - Page Not Found = Requested page/resource doesn't exist
	- 500 - Internal Server Error = Server encountered some form of error with client request that it doesn't know how to handle properly
	- 503 - Service Unavailable = Server unable to handle client request as either overloaded or down for maintenance


**Cookies**
- Small pieces of data stored on a device upon visiting a website.
- Get saved when a `Set-Cookie` header is received from a web server, after which every request made by the client sends cookie data back to the web server
- Due to HTTP being stateless, cookies can be used to remind a web server who the client is i.e personal settings or if the client has visited the site previously.
- Most commonly used for website authentication, in this case the cookie value is usually a token (unique code that isn't easily human guessable) as opposed to a plain-text string in order to protect passwords. 
	- i.e. remember me check boxes - when a user logs in with the box ticked the web server send a `Set-Cookie` HTTP response with the user's login details to the client and tells it to remember them for next time.


## **Summary**
- HyperText Transfer Protocol (HTTP) = The rules that define how requests and responses are sent between a client and a server for a website
	- Stateless - Acts as if every request is its own individual instance as opposed to being connected to a previous one, doesn't retain state
	- Typically communicates via port 80 unless stated otherwise
- HyperText Transfer Protocol Secure (HTTPS) = The same as HTTP but provides encryption through the use of TLS/SSL (Transport Layer Security)
	- Typically communicates via port 443 unless stated otherwise

- Uniform Resource Locator (URL) = Instructions given to a browser that it then uses to request specific pieces of data for a web page from a web server. Made up of multiple parts though most are optional/extra bits of information to increase specificity:
	- Scheme = The protocol being used, i.e. HTTP/HTTPS
	- User = Where a user can login with their credentials should the page allow it
	- Host = The domain name of the web page
	- Port = The port on the web server to which the client is connected to
	- Path = The specific file path the browser has been provided to reach the specified web page
	- Query String = Extra information that can be sent to the requested path such as the specific page number of a blog
	- Fragment = A specific point on a page if the dev has setup those "checkpoints", the browser will load and jump the client straight to the requested point

- HTTP(S) Methods = The syntax used to make requests to a web server that uses HTTP(S), some examples of the most common methods are:
	- GET - Requests data from the web server
	- PUT - Sends data to the web server and can create new records
	- POST - Used to update (Partially modify) existing information on a web server 
	- DELETE - Removes data from a web server

- When Making a requests the client must use headers to inform the web server of the type of information they're using as well as other info such as the browser they're using, some headers include:
	- Host - Domain name or IP address of requested page, if left blank server will send its default web page
	- User-Agent - The browser and version the client is requesting from
	- Content-Length - How long the expected content should be, allows the server and client to ensure none is lost/missing after the response
	- Accept-Encoding - The selected browser's compression method, allows web server to use appropriate compression method for transmission
	- Cookies - Sends cookie data for the site from local cache to help the web server "remember" the user
	- Referer - The web page that sent the client to this one
	- Requests always end with a blank line to inform web server that the request is finished

- HTTP(S) Responses = The way that an HTTP(S) server responds to requests, responses also include their own headers, some being:
	- Content-Type - The type of content being sent to the client
	- Content-Length - Used by the client to ensure no data is missing
	- Server - The web server and software version
	- Date - The date, time and timezone of the web server
	- set-cookie - tells the client what fields to save as cookies (assuming client gave permission to do so)
	- Cache-Control - How long contents of response are to be stored on client's cache before they expire
	- Content-Encoding - Method used to compress the data for transmission
	- Responses end with blank line to tell client that response is finished
	- Anything after the blank line is the requested data

- HTTP Status Codes = The responses given prior to the headers to inform the client on the result of their request, there are different types and they fall into different groups:
	- 1xx = Information response = Tells client that the first part of their request was successful and they should send the next part <- *Rare nowadays*
	- 2xx = Successful request = The client's request was successful
	- 3xx = Redirect = The page has been moved and the client will be redirected to its new address
	- 4xx = Client error = There is an issue with the client's request
	- 5xx = Server error = There is an issue with the server

- Some common, specific status codes include:
	- 200 = OK = Client's request was successful, most common when viewing HTTP responses, means that the web server understood the request and is able to send the desired data back to the client
	- 201 = Created = New resource has been created successfully
	- 301 = Moved Permanently = Web Page has moved permanently to a new address, redirects browser to said new address or tells search engines to look there
	- 302 = Found = Web page has moved temporarily and will likely move again in the future, redirects browser to current address or tells search engine to look there
	- 400 = Bad Request = Client or browser request missing expected data/info
	- 401 = Not Authorised = Client currently lacks the permission to access the web page i.e they aren't logged in to the corresponding account
	- 403 = Forbidden = Client cannot access web page even if logged in
	- 404 = Page Not Found = Requested Web page/resource doesn't exist
	- 405 = Method Not Allowed = Client request is not valid for the resource, i.e. using GET on a login page
	- 500 = Internal Server Error = Server encountered an error with client's request that it doesn't know how to handle properly
	- 503 = Service Unavailable = Server unable to handle client request as it's either overloaded or down for maintenance
- Apps can define their own HTTP Status codes as well

- Cookies = Small pieces of data that browsers can store in their cache to be sent to a web server of a previously visited site. Allows for the web server to effectively "remember" a user by receiving information such as user settings or login credentials alongside a HTTP request
	- Web servers tell the browser what to save using the set-cookie header when responding to a request. Browsers will send cached data under the cookie header with each request to the web server so it can use the information appropriately
		- Commonly used for authentication, User passwords are stored as a token which is a string not easily readable to humans so as to protect the password.