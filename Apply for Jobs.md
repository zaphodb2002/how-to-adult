---
share: true
type: "routine"
status: "active"
---
#routine  
# Daily
## Morning
- [ ] Check email #bureaucracy #communication 🥄3 ⏫ 
- [ ] Apply for a job #NotFun #tedious   🥄2 ⏫ 
## Afternoon
## Evening
# Weekly
- [ ] Apply for a job #NotFun #tedious   🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious 🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious   🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious 🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Apply for a job #NotFun #tedious  🥄2 ⏫
- [ ] Certify for EDD Benefits #money #government #tedious 🥄5 🔺 
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
