- Rock Automation to be available in v18
- replacement for workflow triggers
### Automation
- pattern for reacting to things
- Composed of triggers and events
- triggers are activated by components in Rock
### Automation Triggers
- All changes happen post-save
- Can have multiple criteria for triggers
### Automation Events
- Can have multiple things being done by automation
- Drop-down for event types
	- Launch workflow
	- Lava run
	- Log message
### Plugin Support
- Yes!
- Coming in a few dot releases in v18

How long will workflow triggers be supported moving forward? Will there be a migration path to convert existing workflow triggers?

# AI Gen Notes from recording:
1.  Problem with Existing Workflows
  * Old workflows:
    * Custom actions were difficult to manage.
    * Lacked clear names and descriptions.
    * Hard to remember purpose or reason for workflows.
    * Filtering and grouping was cumbersome.
    * Workflows consumed many CPU cycles and were inefficient.
  * Pain points:
    * Confusing bottom-right filters/criteria in UI.
    * Required constant reference to documentation.
    * Precursor triggers were limited and mostly state-level.
2\. Introduction of Automations
  * Concept:
    * Automations replace old, rudimentary workflows.
    * Pattern for reacting to events using:
      1. Triggers (what starts it)
      2. Events (what it does in response)
    * Key features:
      1. One automation can react to a single trigger but fire multiple events.
      2. Streamlined UI for better clarity on what triggers the automation.
3\. Triggers
  * Trigger behavior:
    * Activated by entity changes (e.g., group updates).
    * Monitor for actions like added, modified, deleted.
  * Criteria/Filters:
    * Example: Monitor GroupTypeId for value 17.
    * Options for:
      * Any change
      * Change from a specific value
      * Change to a specific value
      * Change from one value to another
    * Can combine rules with Advanced Syntax (dynamic link/Lava).
      * Supports complex expressions and keyword matching.
    * Matching logic:
      * “All must match” or “Any can match” for execution.
4\. Events
  * Event types:
    1. Workflow: Launches a workflow.
    2. Lava Event: Executes Lava commands.
    3. Logging Message: Writes to internal log.
    4. Internal Event (testing phase): For new CAT system.
  * Event configuration:
    1. Can toggle events active/inactive without deleting automation.
    2. Multiple events can exist under a single automation.
  * Examples of event actions:
    1. Run a workflow with formatted data.
    2. Execute Lava for API calls, custom logic, or database updates.
    3. Log changes or interactions for auditing.
5\. Advanced Behavior
  * Logging & Debugging:
    * Detailed logs available for automation events.
    * Merge fields provide:
      * Changed entity
      * Person who made the change
      * Original values (dictionary)
      * Modified property names
      * Change state (add/update/delete)
    * Performance & Caching:
      * Automations run efficiently but still require care with DB updates.
      * Direct SQL updates could require cache clearing.
      * Lava commands handle cache refresh automatically.
6\. Extensibility & Future Plans
  * Adding new triggers and event types expected in future releases.
  * Community contributions will be possible once UI stability is ensured.
  * Current focus on entity triggers, but potential for more (e.g., people workflows).


#rx #rx2025 