**Car Park**

#### **JavaScript**
- Used in most web pages
- Thanks to Node.js can now be used as a server-side programming language instead of just a client-side one
- Each line must end with a semicolon (;) if they don't end with a block (i.e. {})
	- Prevents errors caused by auto ; insertion
- Primarily Uses:
	- CamelCase naming convention for variables, functions and methods (userName, calculateTotal, getUserProfile)
	- PascalCase used to distinguish constructors and class names (UserProfile)
	- UPPER_SNAKE_CASE used for global immutable constants AKA global constants (API_ENDPOINT)


#### **Variables**
- Created as such:
	- `let guess = 0;` <- defines a variable whose value can change throughout the program
	- `const secretNum = Math.floor(Math.random() * (20)) + 1;` <- defines a variable whose value is constant and thus cannot change throughout the program
		- `Math.floor()` - removes the decimal by rounding down i.e. 7.44 becomes 7
		- `Math.random()` - gives a random decimal between 0 (inclusive) and 1 (not including 1) i.e. 0.372
		- `* 20` - multiplies range from 0 to (almost) 20 i.e. 7.44
		- `+ 1` - shifts the range from 0-19 to 0-20
		- In this use case `secretNum` can be 1, 2, 3, ..., up to 20

- `console.log(data)` - Used to display data (whatever is in the brackets)


#### **Prompting the User for Input**
- **Importing the necessary module exports and stream interfaces:**
	- `import * as readline from "node:readline/promises";` <- imports the **Promise-based API** of Node.js's built-in **readline** module, the * imports all exported members into a single **readline** object
	
	- `import { stdin as input, stdout as output } from "node:process";` <- Retrieves the `stdin`(standard input) and`stdout` (standard output) properties from the Node.js `process` object 
		- Also aliases them -> Creates local variables named `input` and `output` that reference these stream objects
	
	- `const rl = readline.createInterface({ input, output });`
		- `readline.createInterface` <- **The function (method)** on the `readline` namespace
			- Function is **called immediately** in this case
		- `{ input, output }` <- passing an object containing the aliased streams as configuration
		- `const rl =` <- creates the constant `rl` variable to store the interface instance returned by the function, **not the function itself**

- **Taking user input:**
	- `try{}` <- creates a safe environment to prevent program from crashing if something goes wrong
		- `const text = await rl.question("Take a guess: ");`
			- creates a constant variable called `text` and assigns it the value of the user's input
				- `rl.question()` <- built in method of the Interface object created by `readline.createInterface()`
			- `await` <- pauses the system and waits until user responds
				- Needed in Node.js due to it being a runtime environment so libraries are needed to override its default behaviour i.e. forcing it to wait for user input
		- `guess = parseInt(text, 10);` <- parses `text` as an integer of base `10`
			- `parseInt()` method takes the user input and converts it from text into an integer value
	- `finally{}` <- used to clean up after a block of code within a `try{}` block

#### **Conditional Statements**
- if/else method:
	- Used to evaluate a condition and whether it's true or false (boolean)
	- iterates through each statement within its code block
	- example if/else statement:		
		`if (guess < 1 || guess > 20) {`
		    `console.log("That number is out of range. Try again.");`
		`} else if (guess < secret) {`
		    `console.log("Too low, try again.");`
		`} else if (guess > secret) {`
		    `console.log("Too high, try again.");`
		`} else {`
		    `console.log("You got it in", tries, "tries!");`
		`}`

#### **Iterations**
- Achieved through 3 main loops:
	- `for` <- best for known iterations or array processing, contains initialisation, condition, and increment/decrement expressions
	- `while` <- used when number of iterations is unknown and depends on a condition, condition checked before each execution
	- `do ... while` <- Similar to `while` loop but guarantees code block runs at least once because the condition is checked after execution
- Example `while` loop:
	- `while (guess !== secret)` {code block}
