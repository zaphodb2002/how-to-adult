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
[Chips is Healthy and Happy](./Chips%20is%20Healthy%20and%20Happy.md)
[Cosmo is Healthy and Happy](./Cosmo%20is%20Healthy%20and%20Happy.md)

[Fill Dogs Downstairs Water](./Fill%20Dogs%20Downstairs%20Water.md)
[Fill Dogs Upstairs Water](./Fill%20Dogs%20Upstairs%20Water.md)
## Tasks
[Dog Time](./Dog%20Time.md)

[Take dogs outside AM](./Take%20dogs%20outside%20AM.md)
[Take dogs outside Midday](./Take%20dogs%20outside%20Midday.md)
[Take dogs outside PM](./Take%20dogs%20outside%20PM.md)

[Feed Dogs AM](./Feed%20Dogs%20AM.md)
[Feed Dogs Evening](./Feed%20Dogs%20Evening.md)



# Weekly
## Goals
## Tasks
# Monthly
## Goals
- [ ] Buy dog food #shopping #InTown #kahoots #🐕 🆙+10
## Tasks
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
