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
## Goals
## Tasks
- [ ] Check on the toilet paper situation #BePrepared #survivalSkills #littlePush 🥄+1 🔼 
- [ ] Tidy away 1 thing in the Master Bath #littlePush #tidying #challenge 🥄2
# Weekly
## Goals
## Tasks
- [ ] Tidy [Master Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Master%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Master Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Master%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Master Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Master%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Clean [Master Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Master%20Bath.md) for 15 minutes #🧹 #cleaning  #challenge #myHouse 🥄5
- [ ] Organize [Master Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Master%20Bath.md) for 15 minutes #🧹 #organizing  #challenge #myHouse 🥄5
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
