### Session 4 - Conditional Logic
- {% case var %} then when var to set up switch case
- Boolean Values 
	- | IsInSecurityRole:int to check for access in Lava
	- For boolean comparisons in Lava, get attribute 'RawValue'
### Session 5 - Iterating
- For Loops
	- for loops can be iterated reversed using the keyword reversed
	- can be limited using limit:int
	- offset to skip the number of items in the array
	- can use {% else %} tag within a for loop to output after end of array
	- {% break %} to exit loop
	- {% continue %} bypasses the rest of the loop to start over
- Cycle
	- {% cycle 'John', 'Paul', 'George', 'Ringo' %} - each time cycle is run, it outputs next value in array
		- NOTE: can be used to cycle between colors to differentiate between rows
		- Also note, cycle will go back to start of list once reached
		- Also also note, cyle can be called at any point in the page and it will continue to iterate
	- Can name the cycle to have multiple on the page {% cycle 'var': items %}
- Going Meta
	- info about the loop itself
		- forloop.property to access the below properties
			- index, rindex
			- index0, rindex0
			- first
			- last
### Session 6 - Debugging
- 
