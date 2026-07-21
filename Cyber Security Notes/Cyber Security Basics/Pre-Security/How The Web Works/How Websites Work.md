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