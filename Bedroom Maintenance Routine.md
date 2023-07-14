---
share: true
type: "routine"
sub-type: "maintenance"
status: "available"
created: NaN 
modified: NaN
---
  #routine

# Daily
- [ ] Tidy 1 thing in the bedroom #tidying #littlePush #challenge 🥄+2
# Weekly
- [ ] Tidy [Bedroom](./Bedroom.md) for 15 minutes #habit #tidying #challenge #myHouse 🥄5
- [ ] Clean [Bedroom](./Bedroom.md)  for 15 minutes #habit #cleaning  #challenge #myHouse 🥄5
- [ ] Organize [Bedroom](./Bedroom.md)  for 15 minutes #habit #organizing  #challenge #myHouse 🥄5
# Monthly
- [ ] Wash sheets #cleaning #sleep 🥄2
- [ ] Put sheets on bed #tidying #sleep 🥄5
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
