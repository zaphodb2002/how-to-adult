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
- [ ] Eat Breakfast #habit #Food  🥄+2 ⏫
- [ ] Eat Lunch #habit #habit #Food  🥄+2 ⏫
- [ ] Eat Dinner #habit #habit #Food  🥄+2 ⏫
- [ ] Have a snack #Food  🥄+1
- [ ] Have a snack #Food  🥄+1
- [ ] Drink Coffee #caffeine #adhd  🥄+2
- [ ] Drink Coffee #caffeine #adhd  🥄+2 
- [ ] Drink an Energy Drink #caffeine #adhd  🥄+3

# Weekly
- [ ] Prep a meal #cooking #Food  🥄+5
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
