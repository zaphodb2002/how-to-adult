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
# Weekly
- [ ] Tidy [Entryway](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Entryway.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Entryway](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Entryway.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄 🆙+1
- [ ] Tidy [Entryway](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Entryway.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
Clean [Entryway](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Entryway.md) for 15 minutes #🧹 #cleaning  #challenge #myHouse 🥄3 🆙+3
Organize [Entryway](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Entryway.md) for 15 minutes #🧹 #organizing  #challenge #myHouse 🥄3 🆙+3 
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
