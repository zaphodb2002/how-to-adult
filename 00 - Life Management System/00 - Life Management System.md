---
share: true
alias: "Life Management System"
type: "campaign"
created: NaN
modified: NaN
---
# Things to Sort
#LMS

# Aspects
```dataviewjs
let folder = dv.current().file.folder;
let pages = await dv.pages('"'+folder+'"')
		.where(page => page.file.frontmatter['type'] == 'aspect').file.link

dv.list(pages)
```


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
```dataviewjs
let tasks = dv.pages('"' +dv.current().file.folder+'"').file.tasks
		.where(task => task.status == 'x');
//console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```



- [x] New Routine: Interface with Google Note for [Steph](../03%20-%20Belonging%20%F0%9F%91%AA/01%20-%20The%20Clan/Stephanie%20Fear.md)'s list #LMS #workflow #askingForHelp 🍅1 🥄1 🆙+1 ➕ 2023-07-15 🛫 2023-07-17 ✅ 2023-07-17



- [x] Fixed Routines population to populate from any folder #LMS #programming #javascript #bug 🥄2 🆙+2 ✅ 2023-07-20










- [x] Work the LMS for 30 min #LMS #bureaucracy 🥄5 ✅ 2023-07-07
- [x] Work the LMS for 30 min #LMS #bureaucracy 🥄5 ✅ 2023-07-07
- [x] Refactored Daily Notes template #LMS #tinkering 🥄2 ✅ 2023-07-07
- [x] Refactor the habit tracker #LMS #programming #javascript 🥄5 🛫 2023-07-07 ✅ 2023-07-07


- [f] Do the first thing due today #LMS #adhd #challenge 🥄+1 📅 2023-07-06
- [f] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄+1 📅 2023-07-06


- [x] Do the first thing due today #LMS #adhd #challenge 🥄+1 📅 2023-07-05 ✅ 2023-07-05
- [x] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄+1 📅 2023-07-05 ✅ 2023-07-07




- [x] Do the first thing due today #LMS #adhd #challenge 🥄+1 📅 2023-07-04 ✅ 2023-07-04
- [x] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄+1 📅 2023-07-04 ✅ 2023-07-04






- [x] Do the first thing due today #LMS #adhd #challenge 🥄1 📅 2023-07-03 ✅ 2023-07-03
- [x] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄1 📅 2023-07-03 ✅ 2023-07-03



- [f] Do the first thing due today #LMS #adhd #challenge 🥄1 📆2023-07-03
- [f] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄1 📆2023-07-03


- [f] Record Spoons Info for the day #LMS 🥄1 📆2023-07-03


- [f] Do the first thing due today #LMS #adhd #challenge 🥄1 📆2023-07-01
- [f] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄1 📆2023-07-01


- [f] Record Spoons Info for the day #LMS 🥄1 📆2023-07-01

- [x] Worked on refactoring my routines #LMS #design 🥄15 ✅ 2023-07-04
- [x] Create Daily Note #habit #LMS 🥄+1 🔺 📅 2023-06-30 ✅ 2023-06-30
- [x] Work [Maintenance Views > Tasks scheduled in the past](./02%20-%20Tools/Maintenance%20Views.md#Tasks%20scheduled%20in%20the%20past) #LMS 🥄3 📅 2023-06-30 ✅ 2023-06-30
- [f] Do the first thing due today #LMS #adhd #challenge 🥄1 📆2023-06-30
- [f] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄1 📆2023-06-30
- [f] Sort tasks from Daily Note into Campaigns #habit #LMS #sorting 🍅2 🥄2 🆙+4  📆2023-06-30
- [f] Sort loose files into their appropriate Aspect #LMS 🥄+1  📆2023-06-30
- [-] Record Spoons Info for the day #LMS 🥄1 📆2023-06-30




