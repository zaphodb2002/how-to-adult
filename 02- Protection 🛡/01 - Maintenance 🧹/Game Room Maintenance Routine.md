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
[Tidy away 1 thing in the Game Room](./Tidy%20away%201%20thing%20in%20the%20Game%20Room.md)

# Weekly
## Goals
## Tasks
[Tidy Game Room 01](./Tidy%20Game%20Room%2001.md)
[Tidy Game Room 02](./Tidy%20Game%20Room%2002.md)
[Tidy Game Room 03](./Tidy%20Game%20Room%2003.md)
[Tidy Game Room 04](./Tidy%20Game%20Room%2004.md)
[Tidy Game Room 05](./Tidy%20Game%20Room%2005.md)

Clean [Game Room](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Game%20Room.md) for 15 minutes #🧹 #tidying #challenge #myHouse 🥄5
Organize [Game Room](../../01%20-%20Subsistence%20%F0%9F%92%97/08%20-%20Location%20%F0%9F%A7%AD/Game%20Room.md) for 15 minutes #🧹 #tidying #challenge #myHouse 🥄5
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
