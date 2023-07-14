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
- [ ] Brush Your Hair #habit #hygiene #grooming #hair 🥄1 ⏫
- [ ] Take A Shower #habit #hygiene #grooming #stinky #wet 🥄3 ⏫ 
- [ ] Brush Your Teeth #habit #hygiene #grooming 🥄5 🔺 
- [ ] Put on Deodorant #habit #hygiene #grooming 🥄1 ⏫ 
# Weekly

# Monthly
- [ ] Trim the beard #habit #hygiene #grooming #style 🥄2
- [ ] Trim the bush #habit #hygiene #grooming 🥄4
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
