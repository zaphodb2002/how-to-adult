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

- [ ] Enjoy [Steph's Upstairs 20 Gallon Long Aquarium](Steph's%20Upstairs%2020%20Gallon%20Long%20Aquarium.md) #🐟 #advantage/fun #advantage/relaxing 🍅1 🥄0 🆙+1

- [ ] Enjoy the [Steph's Upstairs 10 Gallon Shrimp Aquarium](Steph's%20Upstairs%2010%20Gallon%20Shrimp%20Aquarium.md) for 5 minutes #🐟 #advantage/fun #advantage/relaxing 🍅1 🥄0 🆙+1



# Weekly

# Monthly
- [ ] Buy Fry Food for upstairs #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Sinking Wafers for upstairs #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Fry Food for TV area #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Sinking Wafers for TV Area #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Fry Food for Bedroom #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Sinking Wafers for Bedroom #shopping #🐟 #AquariumCoop 🥄1
# Seasonally
- [ ] Buy Liquid Carbon for TV area #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Liquid Carbon for upstairs #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Liquid Carbon for Bedroom #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Catappa Leaves for TV Area #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Catappa Leaves for Upstairs #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Catappa Leaves for Bedroom #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Course Sponge Pad #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Water Polishing Pad #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Test Strips for Bedroom #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Test Strips for TV Area #shopping #🐟 #AquariumCoop 🥄1
- [ ] Buy Test Strips for Upstairs #shopping #🐟 #AquariumCoop 🥄1
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
