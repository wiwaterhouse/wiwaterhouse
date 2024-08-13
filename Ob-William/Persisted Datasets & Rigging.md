Rigging patterns

- Persisted datasets
	- stores in JSON
	- Lava can be written as an entity command to loop through and write to JSON
	- Can use ToJSON lava filter to write to JSON as well
	- Don't oversimplify to make sure it's limited to just needed data
	- to get data, use the PersistedDataset lava filter
- Rigging to scale for future, no extra config on the individual page
	- Entity commands are slow by themselves
	- Datasets are stored in memory on IIS, no database pings required
	- 