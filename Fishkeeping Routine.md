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



- [ ] Enjoy the [Upstairs 27 Gallon Aquarium](Upstairs%2027%20Gallon%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2


- [ ] Enjoy [Steph's Upstairs 20 Gallon Long Aquarium](Steph's%20Upstairs%2020%20Gallon%20Long%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2

- [ ] Enjoy the [Steph's Upstairs 10 Gallon Shrimp Aquarium](Steph's%20Upstairs%2010%20Gallon%20Shrimp%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2

- [ ] Enjoy the [Bedroom Iwagumi 20 Gallon Long Aquarium](Bedroom%20Iwagumi%2020%20Gallon%20Long%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2


- [ ] Enjoy the [Bedroom Utility 10 Gallon Aquarium](Bedroom%20Utility%2010%20Gallon%20Aquarium.md) for 5 minutes #fishies #fun #relaxing 🥄+2


# Weekly

- [ ] Scrub Glass on Upstairs 27 Gallon Tank #fishies 🥄3
- [ ] Top Off Upstairs 27 Gallon Tank #fishies 🥄2
# Monthly

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
