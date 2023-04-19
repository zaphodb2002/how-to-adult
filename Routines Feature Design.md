---
share: true
type: "knowledge"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---
# Summary
 
#feature #design
# What does this Feature do?
Routines are the things we need to do on some regular interval.
These tasks need to be correctly created or reactivated or something when their time arrives.  It also needs to set the correct dates, 

# Why does it need to be a Feature?
[Obsidian Tasks](./Obsidian%20Tasks.md) has a recurring task feature but it's a bit sloppy.  At the very least it needs to be 

# Describe the workflow
1. A New Routine task is created and assigned to a mission.
2. The New Routine task is completed by creating a Routine Page from the appropriate Template, and linking the Routine in the Campaign's Routines Aspect.
3. When the appropriate day arrives for the routine's task (either daily, Mondays for Weeklies, first of the month for Monthlies, first day of the season for Season, and first day of the year for yearlies) and that routine is active, the correct interval note template (again, daily, weekly, etc) will populate any due tasks for that interval and set their dates correctly via a script (to be pulled out of the current [rolloverDailyTodos.js](./00%20-%20Life%20Management%20System/06%20-%20Scripts/rolloverDailyTodos.js.md))
4. This script will also fail any routine tasks remaining on the previous day.
5. These will of course be viewable in the interval notes, where we do a lot of work.  The most urgent one for each time slot (morning, afternoon, or evening) will be displayed in the [Routine Tracker](./Routine%20Tracker.md) on the side.
6. History can later be pulled by looking at the routines header in the daily notes.
7. 

# What is the *fastest* way to implement this Feature?
Probably using [Obsidian Tasks](./Obsidian%20Tasks.md).  The issue is that it dumps a load of crap into those routines, and not into the daily note.  However, do I actually need it to be in the daily note?  Maybe not, but that's the way it makes most sense to me.  It's also possible there's another plugin that can do this sort of thing.

# What is the *best* way to implement this Feature?
I think we use [Templater](./Templater.md) to create new tasks from the Routines, effectively treating them like little templates.  We're already doing this in the rolloverDailyTodos.  Ideally, we'd break up each of these chunks into their own scripts.

# So what's the plan?
I think we do it the right way.  I have more control and we still benefit from all of [Obsidian Tasks](./Obsidian%20Tasks.md) stuff except recurrence.

# Components
## Template
[Routine Template](./Routine%20Template.md)
## Display
[Routine Tracker](./Routine%20Tracker.md)
## Manipulation

