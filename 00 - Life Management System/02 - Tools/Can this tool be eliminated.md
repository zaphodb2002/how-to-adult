---
share: true
type: "mission"
status: "completed"

created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---
# Summary
#programming 
quest:: [Build the System](./Build%20the%20System.md)
started:: [2023-03-02](../09%20-%20Daily%20Notes/2023-03-02.md)
completed:: [2023-03-07](../09%20-%20Daily%20Notes/2023-03-07.md)

The answer is yes, we don't need the [Rollover Daily To-dos](./Rollover%20Daily%20To-dos.md) plugin. I have successfully replaced it with [Templater](./Templater.md) and [JavaScript](JavaScript.md).
# Tasks
- [x] Modify [rolloverDailyTodos.js](rolloverDailyTodos.js.md) to delete the rolled over tasks from the previous day ⏫ 📅 2023-03-20 ✅ 2023-03-23
- [x] If [rolloverDailyTodos.js](rolloverDailyTodos.js.md) cannot be modified to delete rolled over tasks, try [Rollover Daily To-dos](./Rollover%20Daily%20To-dos.md) plugin again ⏫ 📅 2023-03-20 ✅ 2023-03-23

- [x] 🔼 Rollover is bringing completed tasks over. That shouldn't happen. ➕ 2023-03-08 📅 2023-03-10 ✅ 2023-03-08
- [x] check tomorrow to see if the rollover worked correctly. ➕ 2023-03-08 ⏳ 2023-03-09 📅 2023-03-09 ✅ 2023-03-10
- [x] 🔼 When tasks roll over, they should mark the old ones with a status to show that they were rolled over (either failed or maybe just rolled over) ➕ 2023-03-03 📅 2023-03-17 ✅ 2023-03-17
		- 2023-03-17 08:49 I'm clearly stuck on this. Let's recap.
  		- The issue is that I have to manually go back and delete the rolled over tasks. They should be automatically deleted when they get rolled over.
  		- Potential Fix #1: Templater is using [JavaScript](JavaScript.md) for this rollover. Figure out how to modify the old file, you already have it, just need to figure out how to write to it. 
    		- 09:16 new task created.
  		- Potential Fix #2: If #1 fails, take a look at [Rollover Daily To-dos](./Rollover%20Daily%20To-dos.md) plugin again. The reason we stopped using it was that the routines were broken by it (and also better to have fewer tools, honestly), but routines are busted anyway and their current configuration shouldn't even be affected by this. Prioritize this over the routines for now.
    		- 09:16 new task created.
  		- Either way, we need a mission/quest for fixing the Routines.
    		- 09:16 Created on [2023-03-17](../09%20-%20Daily%20Notes/2023-03-17.md)
		- 2023-03-11 20:05 haven't gotten to this, easy enough to just go back and remove them or whatever for now. Pushing out to next week.
		- 2023-03-10 22:19 what about potentially just deleting all un-completed tasks on, say, daily notes older than 3 days or something. Run it as a maintenance task (not sure if this could be automated, maybe just in the quickadd or a template macro or something)
		- Need to figure out how to write to other files in templater js.
	- 2023-03-08 13:21 https://notes.nicolevanderhoeven.com/Obsidian+Templater check this for potential solutions
	- 2023-03-06 22:09 this is getting pushed out. Still in progress.
	- failed would imply a routine, something that must be done that day or you fail. I think this is probably better suited for something like a [Implement Habit Tracker](../01%20-%20Gamification/Implement%20Habit%20Tracker.md) tool.
	- rolled over would imply it's a long-running task so we should probably just delete the old ones
- [x] 🔽 Consider making a quest to make a github pr about https://forum.obsidian.md/t/help-now-getting-parsing-error-is-not-a-function-on-all-templates/46345/2 ➕ 2023-03-03 📅 2023-03-17 ✅ 2023-03-17
	- 2023-03-17 09:17 this can be a mission for something else, low priority.
  	- Made a task for this on [2023-03-17](../09%20-%20Daily%20Notes/2023-03-17.md)
	- 2023-03-11 20:08 pushing out, haven't gotten to this.

# Notes

^c38e04

- if DataView doesn't work, there's totally a script in here to make [Templater](./Templater.md) do it.
- I have implemented it in templater, but there are issues
	- does not delete the old tasks (or mark them as failed or something)
	- Pulls the Routines stuff (which I'm pretty sure will be resolved by implementing a proper [02 - Tools](./02%20-%20Tools.md) tool)
	- Does not bring sublists. made a task to fix that.
- 2023-03-06 10:39 Building this out in templater. Using a custom user script [rolloverDailyTodos.js](rolloverDailyTodos.js.md). 
- 2023-03-06 10:40 also implemented the routines as a dataview.


## How to test:
- delete today's note
- recreate today's note

# Things I've Done
- [x] ⏫ Task rollover does not transfer sub-lists. I need that to happen. ➕ 2023-03-04 ⏳ 2023-03-06 📅 2023-03-10 ✅ 2023-03-07
	- 2023-03-07 16:02 Got this part working I think. see [rolloverDailyTodos.js](rolloverDailyTodos.js.md)
	- 2023-03-06 22:10 pushing out, still in progress.
	- 2023-03-07 08:57 So it DOES roll over subtasks. Which makes sense because they're also tasks. What I need is:
		- Identify the list items below and indented after a task until the next blank line or checkbox OR
		- Get access to the T_File and stop using string splitting
			- This is the better option. Make a task for it.

- [x] ⏫ Explain exactly what this tool ([Rollover Daily To-dos](./Rollover%20Daily%20To-dos.md)) does ➕ 2023-03-02 📅 2023-03-02 ✅ 2023-03-02
	- The goal here is to always have whatever needs categorizing listed in the daily note until it gets handled.


- [x] Need to make routines recur. ➕ 2023-03-06 📅 2023-03-06 ✅ 2023-03-06
- [x] ⏫ try to build the functionality with [Templater](./Templater.md) see [^c38e04](Can%20this%20tool%20be%20eliminated.md#^c38e04) ➕ 2023-03-03 📅 2023-03-03 ✅ 2023-03-03
	- I think there might be an issue with Templater's user functions. This needs to be looked into. In the meantime, I will use an inline.
	- So here's the issue https://forum.obsidian.md/t/help-now-getting-parsing-error-is-not-a-function-on-all-templates/46345/2. The problem is that if there is one function in the scripts folder that throws an error, it makes Templater TOTALLY NOT WORK. This is stupid. I have deleted that script from the folder entirely.
	- It works now with the inline.
- [x] ⏫ wait until tomorrow and see if this works correctly ➕ 2023-03-03 ⏳ 2023-03-04 📅 2023-03-04 ✅ 2023-03-05
	- 2023-03-05 10:22 - it did not. there are still outstanding issues. see notes.
- [x] ⏫ Wait until tomorrow and see if this works correctly ➕ 2023-03-02 ⏳ 2023-03-03 📅 2023-03-03 ✅ 2023-03-03
	- It did not.
- [x] ⏫ Go through other installed tools and see if one has similar functionality ➕ 2023-03-02 📅 2023-03-02
	- [DataView](./DataView.md) - probably, it does a lot
		- 
	- Tasks - Also does a lot, there might be a workflow here
	- Templater - maybe, but may need another tool in conjunction (like maybe Periodic Notes, which I'm already interested in)
	- Dice Roller, Emoji Shortcodes, Natural Language Dates, Surfing, all no.
- [x] ⏫ try to build the functionality with [DataView](./DataView.md) ➕ 2023-03-02 📅 2023-03-02 

