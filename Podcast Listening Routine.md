---
share: true
type: "routine"
sub-type: "entertainment"
status: "active"
created: NaN 
modified: NaN
---
  #routine

# Daily
# Weekly
- [ ] Listen to an episode of [Spout Lore](Spout%20Lore.md) #podcast #fun #PtbA #ttrpg #comedy 🥄+2
- [ ] Listen to an episode of [No Dogs in Space](No%20Dogs%20in%20Space.md) #podcast #fun #music #lpotl #history 🥄+2 
# Monthly
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
