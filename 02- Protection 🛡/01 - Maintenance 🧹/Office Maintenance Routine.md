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
[Tidy away 1 thing in the office](./Tidy%20away%201%20thing%20in%20the%20office.md)

Walkway from stairs to Game Room is clear #🧹 #tidying 🥄+1
Path from walkway to chairs is clear #🧹 #tidying 🥄+1
## Tasks

# Weekly
## Goals

## Tasks
[Tidy Office 01](./Tidy%20Office%2001.md)
[Tidy Office 02](./Tidy%20Office%2002.md)
[Tidy Office 03](./Tidy%20Office%2003.md)
[Tidy Office 04](./Tidy%20Office%2004.md)
[Tidy Office 05](./Tidy%20Office%2005.md)

Clean Office #habit #🧹 #cleaning  🍅1 🥄1 🆙+2
Organize Office #habit #🧹 #organizing  🍅1 🥄1 🆙+2
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

```

`$= dv.current()["spoonTotal"]+ "spoons"`