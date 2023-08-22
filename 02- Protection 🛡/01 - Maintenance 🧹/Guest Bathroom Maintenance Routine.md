---
share: true
type: "routine"
sub-type: "cleaning"
status: "available"
created: NaN 
modified: NaN
---
 #routine

# Daily
- [ ] Check on the toilet paper situation #BePrepared #survivalSkills #littlePush 🥄+1 🔼 
- [ ] Tidy away 1 thing in the Guest Bath #littlePush #tidying #challenge 🥄2
# Weekly
- [ ] Tidy [Guest Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Guest%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Guest Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Guest%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Guest Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Guest%20Bath.md) for 5 minutes #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
Clean [Guest Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Guest%20Bath.md) for 15 minutes #🧹 #tidying #challenge #myHouse 🥄3 🆙+3
Organize [Guest Bath](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Guest%20Bath.md) for 15 minutes #🧹 #tidying #challenge #myHouse 🥄3 🆙+3
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
