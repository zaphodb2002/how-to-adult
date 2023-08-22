---
share: true
type: "routine"
sub-type: 
status: "available"
created: NaN 
modified: NaN
---
 #routine

# Daily
# Weekly
- [ ] Play games for an hour #🎮 (part 1) 🥄10 🆙+10
- [ ] Play games for an hour #🎮 (part 2) 🥄10 🆙+10
- [ ] Play games for an hour #🎮 (part 3) 🥄10 🆙+10
- [ ] Play games for an hour #🎮 (part 4) 🥄10 🆙+10
- [ ] Play games for an hour #🎮 (part 5) 🥄10 🆙+10
- [ ] Play games for an hour #🎮 (part 6) 🥄10 🆙+10
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
