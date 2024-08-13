#followup Ask Bema if possible to persist dataset for content channels to keep site fast
also, check to see if persisted dataset can be made for the slowest loading blocks first

Rigging patterns

- Persisted datasets
	- stores in JSON
	- Lava can be written as an entity command to loop through and write to JSON
	- Can use ToJSON lava filter to write to JSON as well
	- Don't oversimplify to make sure it's limited to just needed data
	- to get data, use the PersistedDataset lava filter
	- Can persist properties and attributes
		- must loop through all attribute values so new attributes will be persisted
- Rigging to scale for future, no extra config on the individual page
	- Entity commands are slow by themselves
	- Datasets are stored in memory on IIS, no database pings required
- How to make it easy for staff to set up
	- Option 1, defined values
		- good for structured and recurring functions
		- Rigging template becomes defined type as the only value that is assigned
		- can find first active value in the defined values to use
		- can create a page and limit block to the defined type
	- Option 2, global attributes
		- New global category, add attributes to category
		- use category ID in the rigging persisted dataset template
		- can create a page and limit the block to the category
	- Can build control panels by defining the persisted dataset that is driving the buttons on the page
	- 