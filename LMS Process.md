---
share: true
type: "routine"
status: "active"
---
#routine  
# Daily
- [-] Catch up on any missed days #LMS #adhd 🥄2
- [ ] Create Daily Note #LMS 🥄+1  

- [ ] Do the first thing happening today #LMS #adhd #challenge 🥄+2
- [ ] Do the first thing on the Things To Do List #LMS #adhd #challenge 🥄+2
- [ ] Sort tasks from Daily Note into Campaigns #LMS 🥄1  

# Weekly
- [ ] Sort loose files into their appropriate Aspect  #LMS 🥄1  
- [ ] Sort tasks from Campaigns into Aspects  #LMS 🥄1  
- [ ] Assign tasks from Aspects to appropriate quests  #LMS 🥄1  
- [ ] Assign Tasks from quests to missions  #LMS 🥄1  
- [ ] Work the Maintenance Views for 30 minutes #bureaucracy #sorting 🥄5
- [ ]  Work [Maintenance Views > Tasks scheduled in the past](./Maintenance%20Views.md#Tasks%20scheduled%20in%20the%20past) #LMS  🥄2
- [ ] Work the Weekly Schedule #LMS #sorting 🥄5

```dataviewjs
let spoonChar = '🥄';
let page = dv.current();
let tasks = dv.current().file.tasks
	.where(task => task.text.includes(spoonChar));


let spoonsGained = 0;
let spoonsSpent = 0;

for (let task of tasks)
{
	let givesSpoons = false;
	let startIdx = task.text.indexOf(spoonChar);
	let spoonStr = task.text.substr(startIdx, 5);
	if(spoonStr.includes('+'))
	{
		givesSpoons = true;
	}
	let spoonsValue = parseInt(spoonStr.match(/\d+/g));
	if(givesSpoons)
	{
		spoonsGained += spoonsValue;
	}		
	else
	{
		spoonsSpent += spoonsValue;
	}
	//dv.paragraph(task.text)
	
}

dv.paragraph('+' + spoonsGained);
dv.paragraph('-' + spoonsSpent);
let current = spoonsGained - spoonsSpent
dv.paragraph('spoonTotal:: ' + current);

