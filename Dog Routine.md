---
share: true
type: "routine"
sub-type: 
status: "active"
created: NaN 
modified: NaN
---
  #routine

# Daily
- [ ] Dog time for 10 min #happy #fun 🥄+5
- [ ] Take Dogs Outside AM #doggos  🥄1 ⏫
- [ ] Feed Dogs AM #doggos  🥄1 ⏫
- [ ] Fill Dogs' Downstairs Water #doggos  🥄1 ⏫
- [-] Feed [Sylvie](./Sylvie.md) #cat 🥄1 ⏫ 
- [ ] Take Dogs Outside Noon #doggos 🥄1 ⏫
- [ ] Fill Dogs' Upstairs Water #doggos  🥄1 ⏫
- [ ] Feed Dogs PM #doggos  🥄1 ⏫

# Weekly
# Monthly
- [ ] Buy dog food #shopping #InTown #kahoots #doggos 🥄+10 ⏫ 
# Seasonally
# Yearly

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
