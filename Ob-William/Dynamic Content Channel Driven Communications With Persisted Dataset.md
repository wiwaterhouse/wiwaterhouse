How it works:

1. Content channel

- Updated by ministry teams

3. persisted dataset

- For speed
- Run resource-intensive query once
- Built with lava
- Refresh interval
- Memory cache duration

- As long as the dataset is being accessed, it will keep in memory

- Expires on, date to stop persisting the data
- Entity type
- Allow manual refresh
- Result of lava MUST be in json
- Results must also be in an array
- Keys wrapped in “”
- Can use lava filter ToJSON for help with formatting the objects
- Security enable false to let the script run without interaction

5. lava shortcode

- Lava filter FromCache to prevent a redundant database call

7. communication template

- Shows the lava shortcode  in the communication body

Other uses for persisted datasets

- Content channel item data
- Tags and tagged item relationships
- Washboarding group member
- MORE STUFF, NOTES MISSING

#followup learn more about persisted datasets and lava shortcodes

#RX2022