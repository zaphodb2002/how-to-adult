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
- [ ] Good Mood #cyclothymia #adhd #fun #happy 🥄+5
- [ ] Nice Weather #environment #happy 🥄+2
- [ ] Yucky Weather #environment #unhappy 🥄2
- [ ] Bad Mood #cyclothymia #adhd #NotFun #unhappy  🥄5
- [ ] Adderall Withdrawal #adhd #NotFun 🥄5
- [ ] My back hurts #pain #myBack #old 🥄10
- [ ] Take pain meds #NSAIDsToTheRescue #pain #old 🥄+5
# Weekly
- [ ] Journal Entry #mindfulness #writing 🥄5
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
