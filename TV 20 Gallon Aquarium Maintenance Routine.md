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
- [ ] Enjoy the [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2

# Weekly
- [ ] Feed [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄1 ⏫ 
- [ ] Feed [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄1 ⏫ 
- [ ] Feed [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄1 ⏫ 
- [ ] Feed [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄1 ⏫ 

- [ ] Scrub Glass on [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies #cleaning #wet 🥄5
- [ ] Top Off [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies #wet 🥄2
- [ ] Test water in [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄1 🔼 
# Monthly
- [ ] 30% water change on [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #habit #fishies 🥄5
- [ ] Add a Catappa leaf to [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #fishies 🥄+2
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
