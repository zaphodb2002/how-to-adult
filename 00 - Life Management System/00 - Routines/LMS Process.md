---
share: true
type: "routine"
status: "active"
---
#routine 
# Daily
## Goals
[AM Check In before 0900](../AM%20Check%20In%20before%200900.md)
[Midday Check In before 1300](../Midday%20Check%20In%20before%201300.md)
[PM Check In before 1800](../PM%20Check%20In%20before%201800.md)
[Evening Check In before 2300](../Evening%20Check%20In%20before%202300.md)
[Create Daily Note](../Create%20Daily%20Note.md)
[Check the Weekly Note AM](../Check%20the%20Weekly%20Note%20AM.md)
[Check the Weekly Note PM](../Check%20the%20Weekly%20Note%20PM.md)


## Tasks
[Catch up on a missed day](../Catch%20up%20on%20a%20missed%20day.md)
[Sort tasks from Daily Note into Campaigns](../Sort%20tasks%20from%20Daily%20Note%20into%20Campaigns.md)
[Sort loose files into their appropriate Aspect](../Sort%20loose%20files%20into%20their%20appropriate%20Aspect.md)
# Weekly
## Goals
[Create Weekly Note](../Create%20Weekly%20Note.md)
[Didn't miss a day this week](../Didn't%20miss%20a%20day%20this%20week.md)


## Tasks
[Sort tasks from Campaigns into Aspects](../Sort%20tasks%20from%20Campaigns%20into%20Aspects.md)
[Assign tasks from Aspects to appropriate quests](../Assign%20tasks%20from%20Aspects%20to%20appropriate%20quests.md)
[Assign Tasks from quests to missions](../Assign%20Tasks%20from%20quests%20to%20missions.md)
[Work the Maintenance Views 01](../Work%20the%20Maintenance%20Views%2001.md)
[Work the Maintenance Views 02](../Work%20the%20Maintenance%20Views%2002.md)

# Monthly
## Goals
- [ ] Create Monthly Note #habit #LMS 🥄+1
## Tasks

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

