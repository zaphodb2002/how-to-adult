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
- [ ] Tidy 1 thing in the bedroom #habit #🧹 #tidying #littlePush #challenge 🥄1 🆙+1
# Weekly
- [ ] Tidy [Bedroom](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Bedroom.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Bedroom](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Bedroom.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
- [ ] Tidy [Bedroom](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Bedroom.md) for 5 minutes #habit #🧹 #tidying #challenge #myHouse 🥄1 🆙+1
Clean [Bedroom](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Bedroom.md) for 15 minutes #habit #🧹 #cleaning #challenge #myHouse 🥄5
Organize [Bedroom](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Bedroom.md) for 15 minutes #habit #🧹 #organizing #challenge #myHouse 🥄5
# Monthly
- [ ] Wash sheets #habit #🧹 #cleaning #🛌 (01) 🥄2 🆙+2
- [ ] Wash sheets #habit #🧹 #cleaning #🛌 (02) 🥄2 🆙+2
- [ ] Put sheets on bed #habit #🧹 #tidying #🛌 (01) 🥄5 🆙+5
- [ ] Put sheets on bed #habit #🧹 #tidying #🛌 (02) 🥄5 🆙+5
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
