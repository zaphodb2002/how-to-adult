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
## Goals
## Tasks
[Put dirty clothes in washing machine](./Put%20dirty%20clothes%20in%20washing%20machine.md)


# Weekly
## Goals
[Run the washing machine 01](./Run%20the%20washing%20machine%2001.md)
[Run the washing machine 02](./Run%20the%20washing%20machine%2002.md)

## Tasks
[Move clothes to the drier 01](./Move%20clothes%20to%20the%20drier%2001.md)
[Move clothes to the drier 02](./Move%20clothes%20to%20the%20drier%2002.md)

[Put away clean clothes 01](./Put%20away%20clean%20clothes%2001.md)
[Put away clean clothes 02](./Put%20away%20clean%20clothes%2002.md)


# Monthly
- [ ] Inventory clothes and throw away anything that's damaged or you don't like #clothes #grooming #style 🍅5 🥄5 🆙+10
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
