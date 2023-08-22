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
[Tasks from the Honey-Do List are created in the LMS](../Tasks%20from%20the%20Honey-Do%20List%20are%20created%20in%20the%20LMS.md)
[Honey-Do List is updated with task status from LMS](../Honey-Do%20List%20is%20updated%20with%20task%20status%20from%20LMS.md)
## Tasks
[Check the Honey-Do List](../Check%20the%20Honey-Do%20List.md)

# Weekly
## Goals
[Finish 1 task on the Honey-Do List](../Finish%201%20task%20on%20the%20Honey-Do%20List.md)

## Tasks
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
