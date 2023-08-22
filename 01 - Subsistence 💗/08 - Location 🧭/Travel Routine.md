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

# Weekly
[Check the mail 01](../Check%20the%20mail%2001.md)
[Check the mail 02](../Check%20the%20mail%2002.md)
[Go Supplies Shopping](../Go%20Supplies%20Shopping.md)
[Shop at Stater Bros](../Shop%20at%20Stater%20Bros.md)
[Shop at Target](../Shop%20at%20Target.md)
[Shop at Costco](../Shop%20at%20Costco.md)
[Shop at Walmart](../Shop%20at%20Walmart.md)
[Shop at Fish Store](../Shop%20at%20Fish%20Store.md)




# Monthly
- [ ] Go to Parents' House #🧭 #zone/ramona 🍅15 🥄15 🆙+30
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
