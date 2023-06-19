---
share: true
type: "routine"
sub-type: "cleaning"
status: "active"
created: NaN 
modified: NaN
---
  #routine

# Daily
- [ ] Keys in the box #adhd #BePrepared #challenge 🥄+1
- [ ] Wallet in the box #adhd #BePrepared #challenge 🥄+1
- [ ] Shoes on the rack #adhd #BePrepared #challenge 🥄+1
# Weekly
- [ ] Tidy [Entryway](./Entryway.md) for 15 minutes #tidying #challenge #myHouse 🥄5
- [ ] Clean [Entryway](./Entryway.md) for 15 minutes #cleaning  #challenge #myHouse 🥄5
- [ ] Organize [Entryway](./Entryway.md) for 15 minutes #organizing  #challenge #myHouse 🥄5
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
