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
- [ ] Feed TV 20 Gallon Tank #fishies 🥄1
- [ ] Feed TV 10 Gallon Tank #fishies 🥄1
- [ ] Feed Hospital Tank #fishies 🥄1
- [ ] Feed Upstairs 27 Gallon Tank #fishies 🥄1
# Weekly
- [ ] Scrub Glass on TV 20 Gallon Tank #fishies #cleaning 🥄2
- [ ] Top Off TV 20 Gallon Tank #fishies 🥄2
- [ ] Scrub Glass on TV 10 Gallon Tank #fishies 🥄2
- [ ] Top Off TV 10 Gallon Tank #fishies 🥄2
- [ ] Scrub Glass on Hospital Tank #fishies 🥄2
- [ ] Top Off Hospital Tank #fishies 🥄2
- [ ] Scrub Glass on Upstairs 27 Gallon Tank #fishies 🥄3
- [ ] Top Off Upstairs 27 Gallon Tank #fishies 🥄2
# Monthly
- [ ] 30% water change on TV 20 Gallon Tank #fishies 🥄5
- [ ] 30% water change on TV 10 Gallon Tank #fishies 🥄5
- [ ] 30% water change on Hospital Tank #fishies 🥄5
- [ ] 30% water change on Upstairs 27 Gallon Tank #fishies 🥄10
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
