Clean, consistent, performant

Formatting:

- Keywords always UPCASE
- Table, Field, Field Alias names go `[in brackets]
- Write out INNER JOIN, LEFT OUTER JOIN, RIGHT OUTER JOIN, etc…
- Always write out AS for aliases, for clarity
- Tab to indent under, single space after comma, comma at beginning of line
- Joins go in FROM

Comments:

- Put in good comments for documentation
- use single line for helping identify id numbers
- Move ID numbers to top with comment label, then use the var in the query, - - - divider line
- Under declares, description block of comment
- Title block up at the top (work on template with Traci) separated by === divider

Tips for performance and scale:

- Use EXISTS statement instead of IN for subquery where trying, same for NOT EXISTS
- Avoid using functions in WHERE clause, use CAST AS
- GROUP BY unique values first
- use TOP whenever possible
- put HAVING statement in the WHERE clause, it is computed after the query, will increase compute time
- List out each column you know you need, label each one in the SELECT
- Be explicit in ORDER BY, list the column name instead of number ie p. `[LastName]
- Avoid using DISTINCT, can use GROUP BY to get similar result
- Avoid `%%` wildcards, try to use single % and be as specific as possible
- Can use SET NOCOUNT ON if you don’t need to know how many rows for a query
- Use IN statements instead of lots of OR statements
- Use BETWEEN instead of two AND statements
- Don’t put numbers INTs in ‘

Execution Plans:

#followup Check to see if can enable on TablePlus

Indexes, scans, seeks

- Scan
- Seek

Can create a new index for much more complicated queries that access lots of data in database, limit usage to only where needed

#note BlackBox = Declare any variables for the query at the top

#note SQL style guide on rock community

#note Triumph resources site for more stuff

#RX2022