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
# Weekly
- [ ] Check ynab #capitalismSux #BePrepared #money #anxiety #NotFun  🥄5
# Monthly
- [ ] Pay water bill #money #NotFun #anxiety  🥄3
- [ ] Verify the mortgage got paid #money #NotFun #anxiety 🥄+10
- [ ] Verify the electricity bill #money #NotFun #anxiety 🥄+10
- [ ] Verify the trash bill got paid #money #NotFun #anxiety 🥄+10
- [ ] Verify the internet bill got paid #money #NotFun #anxiety 🥄+10
- [ ] Check to see what other things you might be paying for #money #NotFun #anxiety 🥄5
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
