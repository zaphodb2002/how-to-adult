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
## Goals
## Tasks
[Tidy away 1 thing in the kitchen](./Tidy%20away%201%20thing%20in%20the%20kitchen.md)
[Put away clean dishes from dishwasher](./Put%20away%20clean%20dishes%20from%20dishwasher.md)
[Fill dishwasher](./Fill%20dishwasher.md)
[Start dishwasher](./Start%20dishwasher.md)
[Put dirty dishes in sink](./Put%20dirty%20dishes%20in%20sink.md)
# Weekly

## Goals
## Tasks
[Take out trash to curb](./Take%20out%20trash%20to%20curb.md)
[Tidy Kitchen for 5 minutes 01](./Tidy%20Kitchen%20for%205%20minutes%2001.md)
[Tidy Kitchen for 5 minutes 02](./Tidy%20Kitchen%20for%205%20minutes%2002.md)
[Tidy Kitchen for 5 minutes 03](./Tidy%20Kitchen%20for%205%20minutes%2003.md)
[Tidy Kitchen for 5 minutes 04](../Tidy%20Kitchen%20for%205%20minutes%2004.md)
[Tidy Kitchen for 5 minutes 05](../Tidy%20Kitchen%20for%205%20minutes%2005.md)




Clean [Kitchen](../08%20-%20Location%20%F0%9F%A7%AD/Kitchen.md) for 15 minutes #🍎 #tidying #myHouse 🥄3 🆙+3
Organize [Kitchen](../08%20-%20Location%20%F0%9F%A7%AD/Kitchen.md) for 15 minutes #🍎 #tidying #myHouse 🥄3 🆙+3

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
