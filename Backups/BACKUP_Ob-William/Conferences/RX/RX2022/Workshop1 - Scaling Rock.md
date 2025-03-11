Enterprise Software

Characteristics of Software

Scale, Quality, Extensibility, Innovation

^at war with each other

Scale & Quality vs. Extensibility & Innovation

Innovation - one can break nothing only when doing nothing. Quality suffers

Extensibility - 

Scale

Remove friction

Efficiency is hard to see

Always moving to make Rock more efficient

Things to keep in mind for Rock:

- How often will this feature be used
- what is the usage pattern

- is spread out over a large amount of time
- does it all happen in a compressed amount of time

- What is the impact of each use

- database reads
- database writes - takes longer than read
- iterations

Workflows, sometimes more efficient to not persist, store data other ways

Things to avoid

- Workflow triggers
- complex workflows (esp those with burst traffic usage)

- load test before rollout

- Building ‘applications’ using extensible components
- auditing
- logging

- turn off on all live workflows

Challenge ourselves with the reason why we are doing things

Reach out to Rocket Chat for more reasons

#note Architecture videos for Rock on triumph site

“A working solution is not necessarily a good solution.” PowerPoint Author

Count your database calls, database calls has a free plugin to help with this

Cache is a MUST

“A true genius admits that he/she knows nothing.”

#RX2022