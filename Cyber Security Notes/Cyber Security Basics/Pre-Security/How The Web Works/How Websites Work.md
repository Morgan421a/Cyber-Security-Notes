**How Websites Work**
- Upon visiting a website the user's browser makes a request to a web server asking for info about the page.
	- Web server responds with data which the browser uses to render the page
- Web Server = Dedicated computer that handles user requests
- Two major components make up a website:
	- Front End (Client-side) - The way a browser renders the website
	- Back End (Server Side) - A server which processes user requests and returns a response
- Primarily created using:
	- HTML - Build websites and define their structure
	- CSS - style the appearance of a website
	- JavaScript - Implementing more complex features using interactivity
**HTML**
- The language websites are written in
- Uses elements (AKA tags) to tell browsers how to display content
- [[HTML Elements|Here]] Are some basic HTML elements
- Attributes can be placed inside tags to style them such as changing the style of text using `<p class="bold text">`
	- They can also be used for other purposes such as the `src` tag which can be used to specify the location of an image `<img src=img/cat.jpg>`
	- The `id` attribute is used for styling and identifying an element using JavaScript. Unique to each element they're in. 
	- *Technically `id` and `class` only used to provide metadata/identification so that the CSS and JS can target a specific element to style or control*

**JavaScript (JS)**
- A Programming language used to make web pages interactive, controls the functionality
- Added within page source code and loaded within the `<script>` element
	- Can also be added remotely via `<script src="/location/of/javascript_file.js"></script>`
- Can also have events like "onclick" or "onhover" to execute JS when the event happens e.g.
	- `>button onclick='document.getElementByID("demo").innerHTML = "Button Clicked";'>Click Me!</button>` - onclick event can also be defined inside JS script tags and not on elements directly

**Sensitive Data Exposure**
- Occurs when a website doesn't properly protect/remove sensitive clear-text info to the end-user as such that it can be found in the site's frontend source code i.e. login details, hidden links to private parts of site or other sensitive data
- Info can be used to further attacker's access within other parts of a web app

**HTML Injection**
- Client-Side vulnerability caused through lack of sanitising user input prior to displaying it on the page
- Allows users to inject HTML or JS code into website giving them control over page's functionality and appearance
- General rule to Never Trust User Input
- All user input should be sanitised before it's used in JS functions or displayed on the page i.e. removing HTML tags before passing it to either.


## **Summary**
- Websites are built using HTML, JavaScript (JS) and CSS
- They have a frontend and a backend
	- frontend = client side, what the user sees
	- backend = server side, what communicates with the server
- HTML - Defines the language and structure of the website, it's responsible for putting content on the page itself using elements wrapped in `<>` to open an element and `</>` to close the element i.e. `<p>` Defines a paragraph on the page `</p>`
	- All HTML pages should start by telling the browser what HTML version the page uses so it can interpret the content correctly. This is done by using `<!DOCTYPE HTML>` which in this case tells the browser the page uses HTML5 and should be interpreted as such
	- `<html> </html>` = the root element of the page, all other data should be come after this element
	- `<head> </head>` = Sits directly under the `<html>` element, Contains data that is not displayed on the page itself such as the `<title>` which displays the name of the web page in the browser tab `</title>`
	- `<body> </body>` = Where the main content of the page sits wrapped in their own elements.
	- Some other HTML elements include:
		- `<div> </div>` = Used to identify a section/chunk of a web page's data, helps keep code clean as well as grouping elements for the same purpose together
		- `<h1> </h1>` = Used for headers
		- `<p> </p>` = Used for paragraphs
		- `<img>` = Used for images, no closing tag
		- `<ul> </ul>` = Creates an unordered list that uses bullet points for each entry
		- `<ol> </ol>` =  Creates an ordered list that uses numbers or letters for each entry
		- `<li> </li>` = Creates a list item in either an ordered or unordered list

	- Elements can contain tags within their opening <> to alter their look such as font, colour, weight and size (using CSS) as well as giving them a class or id to provide metadata for JS or CSS to affect specific elements of a web page. An example of a tag within a element would be: `<p id="1" style="color: blue";>some text</p>`
	- tags are also used in other ways, such as identifying the source for an image
		- i.e. `<img src="img/cat.jpg"`

- CSS = Used to style a web page's elements and make them look nice

- JavaScript (JS) = Used to alter a page's elements and add interactivity for the user
	- Can be defined directly within the HTML file using the `<script> </script>` element or can be imported from another file using `<script src="/location/of/JS/file.js"> </script>`
		- Can be programmed to alter the HTML or CSS of elements on the page upon certain actions being taken by the user such as onclick or onhover

- Sensitive Data such as admin login credentials, test login credentials or links to private/hidden pages must not be left in the frontend code as a user can open the dev tools to inspect the code and may find them, giving them unauthorised access to parts of the website or data they shouldn't be able to get to.

- HTML injection is the act of inputting HTML/JS anywhere on a web page such as a login box, URL, Search Bars, etc. To alter it or even seek out private sections or data. 
	- All User input should be deemed untrustworthy by default, it should all be sanitised first before passing it to the backend or frontend to be used on the web page. An example of sanitising input would be to remove any HTML tags before displaying the input on the page.