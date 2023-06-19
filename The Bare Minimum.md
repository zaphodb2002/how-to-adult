---
share: true
type: "routine"
status: "active"
---
#routine 
# Daily
## Morning (0600-1200)
---
- [ ] Slept #sleep 🥄+5 ⏫ 
- [ ] Slept Well #sleep 🥄+5 ⏫ 
---
- [ ] Take Dogs Outside  #doggos  🥄1 ⏫
- [ ] Feed Dogs #doggos  🥄1 ⏫
- [ ] Fill Dogs' Water #doggos  🥄1 ⏫
- [ ] Feed [Sylvie](./Sylvie.md) #cat 🥄1 ⏫ 
- [ ] Eat Breakfast #Food  🥄+2 ⏫
- [ ] Take Meds  #meds #adhd #hbp 🥄+5 ⏫
- [ ] Drink Water #hydration 🥄+2 ⏫

## Afternoon (1200-1800)
- [ ] Take Dogs Outside  #doggos 🥄1 ⏫
- [ ] Eat Lunch #Food  🥄+2 ⏫
- [ ] Take 2nd Adderall (optional) #meds #adhd  🥄+5 ⏫
- [ ] Drink Water #hydration   🥄+2 ⏫

## Evening (1800 - 2400)
- [ ] Fill Dogs' Water #doggos  🥄1 ⏫
- [ ] Eat Dinner #Food  🥄+2 ⏫
- [ ] Feed Dogs #doggos  🥄1 ⏫
- [ ] Brush Your Hair #hygiene #hair 🥄+1 ⏫
- [ ] Take A Shower #hygiene  🥄+3 ⏫
- [ ] Brush Your Teeth #hygiene 🥄+2 ⏫


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
