---
share: true
type: "routine"
sub-type: "maintenance"
status: "active"
created: NaN 
modified: NaN
---
  #routine

# Daily
- [ ] Tidy away 1 thing in the kitchen #tidying #littlePush #kitchen #challenge 🥄+2

# Weekly
- [ ] Put away clean dishes from dishwasher #habit #tidying #kitchen 🥄1
- [ ] Fill dishwasher #tidying #kitchen #habit 🥄5
- [ ] Start dishwasher #cleaning #kitchen #habit 🥄1
- [ ] Put dirty dishes in sink #tidying #kitchen #habit  🥄1
- [ ] Take out trash to curb #cleaning #challenge #myHouse #outside 🥄2
- [ ] Tidy [Kitchen](./Kitchen.md) for 15 minutes #tidying #challenge #myHouse 🥄5
- [ ] Clean [Kitchen](./Kitchen.md) for 15 minutes #tidying #challenge #myHouse 🥄5
- [ ] Organize [Kitchen](./Kitchen.md) for 15 minutes #tidying #challenge #myHouse 🥄5
- [ ] Put away clean dishes from dishwasher #tidying #kitchen 🥄1
- [ ] Fill dishwasher #tidying #kitchen  🥄5
- [ ] Start dishwasher #cleaning #kitchen  🥄1
- [ ] Put dirty dishes in sink #tidying #kitchen  🥄1
- [ ] Put away clean dishes from dishwasher #tidying #kitchen 🥄1
- [ ] Fill dishwasher #tidying #kitchen  🥄5
- [ ] Start dishwasher #cleaning #kitchen  🥄1
- [ ] Put dirty dishes in sink #tidying #kitchen  🥄1

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
