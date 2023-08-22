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
[Went to bed at a reasonable time](./Went%20to%20bed%20at%20a%20reasonable%20time.md)
[Slept](./Slept.md)
[Slept Well](./Slept%20Well.md)
[Used CPAP](./Used%20CPAP.md)

## Tasks

# Weekly
## Goals
[Wash Sheets](../../02-%20Protection%20%F0%9F%9B%A1/01%20-%20Maintenance%20%F0%9F%A7%B9/Wash%20Sheets.md)
[Dry Sheets](./Dry%20Sheets.md)


## Tasks
[Fill CPAP Reservoir](./Fill%20CPAP%20Reservoir.md)
[Clean CPAP](./Clean%20CPAP.md)
[Take Sheets Off Bed](./Take%20Sheets%20Off%20Bed.md)
[Put Sheets on bed](./Put%20Sheets%20on%20bed.md)





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
