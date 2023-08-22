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
```dataviewjs
let tasks = dv.current().file.tasks;
console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```
## Goals

## Tasks
[Enjoy the TV 20 Gallon Aquarium](./Enjoy%20the%20TV%2020%20Gallon%20Aquarium.md)


# Weekly
## Goals
[Feed TV 20 Gallon Aquarium 01](./Feed%20TV%2020%20Gallon%20Aquarium%2001.md)
[Feed TV 20 Gallon Aquarium 02](./Feed%20TV%2020%20Gallon%20Aquarium%2002.md)
[Feed TV 20 Gallon Aquarium 03](./Feed%20TV%2020%20Gallon%20Aquarium%2003.md)



## Tasks
[Rinse out filter sponge on TV 20 Gallon Aquarium](./Rinse%20out%20filter%20sponge%20on%20TV%2020%20Gallon%20Aquarium.md)
[Change Polishing Pad on TV 20 Gallon Aquarium](./Change%20Polishing%20Pad%20on%20TV%2020%20Gallon%20Aquarium.md)
[Scrub Glass on TV 20 Gallon Aquarium](./Scrub%20Glass%20on%20TV%2020%20Gallon%20Aquarium.md)
[Top Off TV 20 Gallon Aquarium](./Top%20Off%20TV%2020%20Gallon%20Aquarium.md)


# Monthly
## Goals
- [ ] Add a Catappa leaf to [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #🐟 🆙+1
- [ ] Test water in [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #🐟 🆙+1 🔼 
## Tasks

- [ ] Record water parameters in [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #🐟 #complication/tedious 🍅1 🥄2 🆙+3
- [ ] 30% water change on [TV 20 Gallon Aquarium](TV%2020%20Gallon%20Aquarium.md) #habit #🐟 #complication/wet  🍅5 🥄6 🆙+11

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
