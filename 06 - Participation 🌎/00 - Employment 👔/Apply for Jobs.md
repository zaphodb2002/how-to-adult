---
share: true
type: "routine"
status: "active"
---
#routine 
# Daily
## Goals
## Tasks
[Check Email](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Check%20Email.md)

# Weekly
## Goals
[Get a Callback](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Get%20a%20Callback.md)
[Complete an Interview](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Complete%20an%20Interview.md)


## Tasks
[Apply for a job 01](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2001.md)
[Apply for a job 02](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2002.md)
[Apply for a job 03](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2003.md)
[Apply for a job 04](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2004.md)
[Apply for a job 05](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2005.md)
[Apply for a job 06](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2006.md)
[Apply for a job 07](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2007.md)
[Apply for a job 08](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2008.md)
[Apply for a job 09](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2009.md)
[Apply for a job 10](../../02-%20Protection%20%F0%9F%9B%A1/04%20-%20Money%20%F0%9F%92%B0/Apply%20for%20a%20job%2010.md)

# Monthly
## Goals
## Tasks
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
