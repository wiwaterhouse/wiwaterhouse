- Every single entity as rock core and what that has access to
- Entity - object in Rock, often with attributes
- database icon Property column on the database
- square icon not mapped to the database, computed in lava
- attributes - array, will return nothing if you try person.attributes, must specify which one
- What entity am I working with? {{ Entity | debug }}
- Make sure you are using the labels in the model map, not the descriptions of things (left side, not right side)
- Attributes, use | pipe
- Properties, use . dot
- Use ‘Object’ to get the full object

Model map is the ‘jump path’ for what you have access to in an entity

#note in v13, registration vs registrant workflow launch

#note try to always use personAlias when working with getting people to make resilient against person merges

#RX2022