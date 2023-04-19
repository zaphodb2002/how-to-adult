---
share: true
alias: "Life Management System"
type: "campaign"
created: <%+ tp.file.creation_date() %>
modified: <%+ tp.file.last_modified_date() %>
---
#LMS
# Things to Sort



# Quests
## Main
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Life Management System";
for (let page of pages)
{
	if(page["sub-type"] == "main" && page["status"] == "active" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + '\n';
}
    
dv.el("div", result)
```

## Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Life Management System";
for (let page of pages)
{
	if(page["sub-type"] != "main" && page["status"] == "active" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```

## Available
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Life Management System";
for (let page of pages)
{
	if(page["status"] == "available" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```

# Aspects
[ 00 - Routines](00%20-%20Life%20Management%20System/00%20-%20Routines/00%20-%20Routines.md)
[01 - Gamification](./01%20-%20Gamification.md)
[ 02 - Tools](00%20-%20Life%20Management%20System/02%20-%20Tools/02%20-%20Tools.md)
[03 - Workflow](./03%20-%20Workflow.md)
[04 - Research](./04%20-%20Research.md)
05 - 
[06 - Scripts](./06%20-%20Scripts.md)
07 - 
[08 - Templates](./08%20-%20Templates.md)
[09 - Daily Notes](./09%20-%20Daily%20Notes.md)


# Goals
- Create Structure
- Invest in Myself
- Foster Mindfulness
- Complete Goals On Time
- Document EVERYTHING
- Everything in one place

# [Design Pillars](Design%20Pillars.md)
1. Produce tangible, measurable results
2. Fractal in design, manage the system like you manage all other projects
3. Limit visible information to only the most important actionable items
4. System is a safety net not a booster
5. There is no reward for doing it perfectly

# Challenges
- ADHD
	- Boredom
	- Overwhelmed
	- Distractions
	- Time Blindness
- Depression
- Decision Paralysis
archived.
# Solutions
### What has worked in the past?
- ADDERALL
- CAFFEINE
- Priority Lists with Prompts
- Short (timed) work periods
- Minimizing distraction (working alone, with headphones, silenced phone)
- linking work to the length of an album, chapter of audiobook, or podcast
- Time Estimates and Tracking
- Designated places for things, preferably easy to see and near where the thing is used
- Breaking down tasks to reasonable size (time estimating helps with this as I'm bad at assessing )
- associating tasks with the Why of them.
- Meditation
- Taking at least one day off a week
- Gamification (Though I struggle with withholding things for reward, need external reward)
- Pleasant Morning Routines (though I often lose them with Depression)
- making things I don't like as easy as possible

### What has not worked?
- Phone Apps (I don't really use my phone that much)
- Habitica (I did all possible things but it worked until then)
- Calendar Events
- Alarms (though they help to mark time)
- Boxes or drawers, anything I can't see into

### What haven't I tried?
- Having an accountability partner
- Keeping a clean workspace
- Positive affirmations
- Managing Expectations (lol)

### What do I like?
- Flow State
- [Mastery](Mastery.md)
- Rules
- Being Clever
- Discovery
- Sorting Things (am I a [Bureaucrat](Bureaucrat.md)?)
- Refactoring

### What do I not like?
- Arbitrarily made decisions (use dice rolls!)
- Cleaning
- Wearing pants
- Exercise!

### What am I trying to accomplish with this document?
- Journal, to record data
- Research, and build knowledge bases
- Document instructions and protocols for managing life for consistency.

# Things I've Done
- [x] New Aspect: Gamification ✅ 2023-03-22
- [x] Removed Quest aspect, was cluttered.  May reimplement later or put elsewhere without missions ✅ 2023-03-22
- [x] Add topic [Gamification](Gamification.md) ➕ 2023-02-28 ✅ 2023-03-03
- [x] Add topic [Concepts](./Concepts.md) ➕ 2023-02-27 ✅ 2023-03-01
- [x] Change wording of Topic to Aspect? ➕ 2023-03-02 ✅ 2023-03-02