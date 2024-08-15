What is lava?
- Templating language
- Define placeholders in HTML that server can inject code into for customization

Lava Syntax
- Variable - an object that lives on the server
- Entity - an object with properties and attributes
- Use a . to access a PROPERTY of the variable
- When doing "work" ie executing code, use {% this %}
- Tags
	- Inline or block (block will have {% endx %})
- Types of values
	- Strings use single ' '
	- Date yyyy-MM-ddTHH:mm:ss is default in database
- Capture tag is used to create and set value of custom variables
- <> can be used to compare text, alphabetical order
- For loops
	- Limit
	- Reversed
	- Offset
- Filters
	- Allow Get first or last in list
	- sort
	- get info from entity
	- get value of an attribute
	- get JSON value of a variable
	- input | filterName: 'Param','SecondParam'
	- can use ToJSON for easy reading for debugging
	- Attribute plus key
	- Group filter to check membership of a certain group

Lava Command
- Must be enabled in block beforehand
- name of entity type {% entitytypename %} then {% endentitytypename %}
	- id, ids, where
	- more results will have var name nameItems\[number]
- Personalize is one for segments if set up
	- otherwise is used as 'else'

Resources
- Lava manual