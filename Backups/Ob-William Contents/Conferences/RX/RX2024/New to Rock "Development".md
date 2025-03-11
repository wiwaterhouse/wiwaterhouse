### It's not just about writing code
Why dev is needed?
- customization
How to access data in rock
- Entities - Typical access within lava, rock UI
	- People
	- Groups
	- Campuses
	- Transactions
- Services - C#
	- read/write data
	- perform calculations
- RockContext - C#
	- Database access
If I REALLY need to write code
- TypeScript
- C#
- JavaScript
- When creating plugins, reusable, new entities
The Parts of Rock
- Blocks
- Cache
- Components
- Data filters
- data selects
- entities
- jobs
- field types
- Workflow actions
- not complete list, there's more
A trip through time
- Original Rock
	- ASP.NET (WebForms) - 2002 is what Rock is built on
	- HTML4
	- CSS2
	- GeoCities
	- Twitter didn't exist
- What's new since then?
	- iPhone
	- HTML5
	- Chrome
	- Websockets - realtime comm between client and server
	- Multitouch on web
	- TypeScript
	- Xbox One
	- Drag and drop on web
	- WebRTC - Video calls, etc via browser
	- Push notifications
- Where are we going
	- Still C#
	- .NET (Core)
	- Cross Platform
	- UI agnostic blocks - same block across multiple platforms for some block types
	- JavaScript UI Framework - offloading processing from server to browser
	- Standard Field Type UI - similar to UI agnostic, trying to separate the data from the UI for easier upgrades in the future
	- 