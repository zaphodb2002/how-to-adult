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
- [ ] Completed 1000 steps #habit #💪 🆙+2
- [ ] Completed 2000 steps #habit #💪 🆙+2
- [ ] Completed 3000 steps #habit #💪 🆙+2
- [ ] Completed 4000 steps #habit #💪 🆙+2
- [ ] Completed 5000 steps #habit #💪 🆙+2
- [ ] Completed 6000 steps #habit #💪 🆙+2
- [ ] Completed 7000 steps #habit #💪 🆙+2
- [ ] Completed 8000 steps #habit #💪 🆙+2
- [ ] Completed 9000 steps #habit #💪 🆙+2
- [ ] Completed 10000 steps #habit #💪 🆙+10

## Tasks


# Weekly
## Goals
- [ ] Record weight #habit #💪 🆙+1
- [ ] Weigh less than 250 lbs #habit #💪 🥄+5
- [ ] Weigh less than 240 lbs #habit #💪 🥄+5
- [ ] Weigh less than 230 lbs #habit #💪 🥄+10
- [ ] Weigh less than 220 lbs #habit #💪 🥄+10
- [ ] Weigh less than 210 lbs #habit #💪 🥄+15
- [ ] Weigh less than 200 lbs #habit #💪 🥄+15
## Tasks
 - [ ] Walk around the block #habit #💪 #complication/pain #complication/depression 🍅5 🥄7 🆙+12
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
