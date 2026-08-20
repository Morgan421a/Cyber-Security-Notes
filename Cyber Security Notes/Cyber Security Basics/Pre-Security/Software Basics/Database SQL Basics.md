**Car Park**

#### **Tables, Rows, and Columns**
- **Database** - Where a computer stores information in an organised way
	- Allows a computer to search, count and sort data quickly
	- data on a database is stored in **tables**

- **Table** - Resembles a spreadsheet, data organised into rows and columns
- **Column** - Titles at the top of the table. Describe the type of data stored
- **Rows** - Go across each table. Each row contains one complete set of data

- **Structured Query Language (SQL)** - A language used to ask questions (queries) of a database
	- A query doesn't change the data, it only displays the requested data from the table

#### **SQL Queries**
- Four core SQL parts:
	- **SELECT** - View specified parts of a table
		- `SELECT *` <- Selects all columns
		- `SELECT <column_name>` <- Select a specific column
		- Can select multiple columns at a time as such:
			- `SELECT column1, column2 FROM <table_name>`
	- **FROM** - Which table to use
		- `FROM Orders;` <- Selects the `Orders` table
		- `FROM <table_name>` <- Select table
	- **WHERE** - Filter rows, keeping only those that match a condition
		- `SELECT * FROM Orders WHERE drink = 'Coffee';`
			- Only selects Orders where Coffee is the drink
		- `SELECT <column> FROM <table> WHERE <column> = <row_data>`  <- select rows based on condition
	- **ORDER BY** - Sorts results by a column, by default results are sorted in ascending order
		- `SELECT * FROM Orders ORDER BY price DESC;` <- Sorts data in descending (reverse) order by price
		- `SELECT * FROM <table> ORDER BY <column> <sort_order>` 
		- Multi-column ORDER BY (e.g. `ORDER BY price DESC, time DESC`) can be used to consistently rank items when primary sort values match.