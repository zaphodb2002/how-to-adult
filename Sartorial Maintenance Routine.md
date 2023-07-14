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
- [ ] Put dirty clothes in washing machine #cleaning #clothes #BePrepared  🥄5 ⏫ 

# Weekly
- [ ] Run the washing machine #cleaning #clothes #BePrepared 🥄1
- [ ] Move clothes to the drier #cleaning #clothes #BePrepared 🥄5 ⏫ 
- [ ] Put away clean clothes #tidying #clothes #BePrepared #challenge #adhd 🥄7
- [ ] Run the washing machine #cleaning #clothes #BePrepared 🥄1
- [ ] Move clothes to the drier #cleaning #clothes #BePrepared 🥄1 ⏫ 
- [ ] Put away clean clothes #tidying #clothes #BePrepared #challenge #adhd 🥄7
# Monthly
- [ ] Inventory clothes and throw away anything that's damaged or you don't like #clothes #grooming #style 🥄5
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
