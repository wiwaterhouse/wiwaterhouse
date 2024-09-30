https://github.com/LPMcDude/CITN_2024
###### Note:
- There are multiple ways to do almost everything. The following is just one way
###### Some Generalities
- RDBMS - Relational Database Management System
- Data is relational, relationships often through foreign keys
- Generally case insensitive
- Fast and scalable
- Expensive
###### Why Azure SQL?
- Licensing included
- Always running latest
- Enterprise edition
###### Tables and Data Storage
- Rock built on Entity Framework, most table records are basically Rock objects with identity Primary Key and many properties
- Stored in 8K data pages
###### Tables - Structures
- Clustered index - needed
	- how entire table data stored with key, 
	- every unique key
- Non clustered indexes
	- secondary index on top of a table or heap,
	- way of sorting data for faster query
	- sometimes non-unique keys
- Primary Keys
- Foreign Keys
- Heaps
###### TIP - table size data size
- sp_spaceused to view sizes, very fast
###### Indexes - What are they?
- Mini tables attached to your base tables that SQL can see but you can't
- B-tree structures
- the key to Read perf
- online=on can run indexes while online
###### Index - Types
- Clustered - only 1 per table
- Non-clustered
- Unique - can be clustered or non
- Covering - include additional columns, not an actual index
###### Indexes - Operations
- Seek
- Scan
- Key Lookup
###### Indexes - Compression
- Improves IO at cost of CPU
- Applies to storage and RAM
###### Indexes - Why not index every column?
- Slower writes
- 20 indexes = 20 insert ops
- DB Bloat
###### 