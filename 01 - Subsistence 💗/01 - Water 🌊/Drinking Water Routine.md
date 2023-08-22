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
## Goals
[Water Bottle Empty 01](./Water%20Bottle%20Empty%2001.md)
[Water Bottle Empty 02](./Water%20Bottle%20Empty%2002.md)
[Drink Water AM](./Drink%20Water%20AM.md)
[Drink Water Noon](./Drink%20Water%20Noon.md)
[Drink Water PM](./Drink%20Water%20PM.md)

## Tasks
[Refill Water Bottle 01](./Refill%20Water%20Bottle%2001.md)
[Refill Water Bottle 02](./Refill%20Water%20Bottle%2002.md)


# Weekly
## Goals
## Tasks
[Replace Bottle](./Replace%20Bottle.md)
[Replace Straw](./Replace%20Straw.md)

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
