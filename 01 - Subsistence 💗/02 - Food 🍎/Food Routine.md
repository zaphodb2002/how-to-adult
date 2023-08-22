---
share: true
type: "routine"
sub-type: "health"
status: "active"
created: NaN 
modified: NaN
---
 #routine

# Daily
## Goals
[Eat Something AM](./Eat%20Something%20AM.md)
[Eat Something Midday](./Eat%20Something%20Midday.md)
[Eat Something PM](./Eat%20Something%20PM.md)
[Eat Something Evening](./Eat%20Something%20Evening.md)


[Ate less than 1200 kcals before 1200](./Ate%20less%20than%201200%20kcals%20before%201200.md)
[Ate less than 2400 kcals before 2200](./Ate%20less%20than%202400%20kcals%20before%202200.md)


## Tasks

# Weekly
## Goals
## Tasks
[Go Grocery Shopping](./Go%20Grocery%20Shopping.md)
[Plan next week's menu](./Plan%20next%20week's%20menu.md)
# Monthly
## Goals
## Tasks
[Inventory Food Stores](../Inventory%20Food%20Stores.md)

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
