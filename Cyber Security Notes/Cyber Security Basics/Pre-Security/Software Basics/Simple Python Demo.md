**Car Park**

**Python**
- High level, General-Purpose programming language
- **Pseudo-Code** = English language that is closer to a programming language i.e. "If the guess is less than 1 or greater than 20, print 'Out of range' (If not the case, proceed to next step)" 
- **Primarily uses**: 
	- **snake_case** for most identifiers e.g. variables, functions, modules, etc. (snake_case, my_variable)
	- **CamelCase** (specifically **PascalCase** or **CapWords**) for class names and exceptions (PascalCase, MyClass) 
		- can be used for variables and function but is considered non-standard and generally discouraged in favour of snake_case
	- **UPPER_SNAKE_CASE** for constants (MAX_VALUE)

**Variables**
- **Variable** = A container for storing data values
- Variable names = **case sensitive**, `a` and `A` are considered different variables
- Created as such:
	- `var_name = 1` <- **integer** (`int`)
	- `x = "Hello World!"` <- **string** (`str`) <- strings can be written with either single quotes (' ') or double quotes (" ") <- rule changes between programming languages
	- `y = 1.5` <- **float** (`float`)

- Types can be specified through **casting**:
	- `x = str(3)` <- x will be "3" (a string)
	- `y = int(3)` <- y will be 3 (an integer)
	- `z = float(3)` <- z will be 3.0 (a float)

- `random.randint()` <- imported from the **random module**, returns a random integer within the specified range i.e. `random.randint(1, 20)` returns a random number between 1 and 20
- `x = input("string of text: ")` <- allows for user input at the end of the string of text
- `y = int(x)` <- can be used to convert data of another type, in this case a string, into an integer (converted number must be an integer otherwise an error is thrown)

**Conditional Statements**
- **If/else function** evaluates a condition and whether it is true or false (boolean)
	- iterates through each statement within its code block 
		- skips false conditions 
		- executes the first true condition (then exits) 
		- if no true condition found then it defaults to the `else:` statement (then exits)
- if/else function example:
	- `if guess < 1 or guess > 20:`
		`print("That number is out of range. Try again.")`
	 `elif guess < secret_num:`
		`print("Too low, try again.")`
	 `elif guess > secret_num:`
		`print("Too high, try again")`
	 `else:`
		`print("you got it in", tries, "tries!")`


**Iterations**
- AKA **Loops**
- **two main loops in python** are: 
	- **`while` loops** - Execute code block repeatedly as long as a specified boolean condition remains true <- good for when exact num of iterations is unknown beforehand
	- **`for` loops** - Iterate over a sequence (i.e. list, tuple, string, range, etc.) when num of iterations is known or fixed, executes code block once for each item in the sequence
- Allow for same code block to be iterated over for as long as a specific condition holds
- N**ested loops** also exist <- Placing one loop inside another, used for complex, multi-layered iterations
- example `while` loop:
	- `while guess != secret_num:` <- repeat until user guesses the secret number
			`text = input("take a guess: ")`
			`guess = int(text)`
