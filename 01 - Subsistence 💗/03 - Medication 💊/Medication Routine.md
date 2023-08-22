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
## Goals
[Take ADHD Meds AM](./Take%20ADHD%20Meds%20AM.md)
[Take Blood Pressure Meds AM](./Take%20Blood%20Pressure%20Meds%20AM.md)
[Take Pain Meds AM](./Take%20Pain%20Meds%20AM.md)
[Take Supplements](../../02-%20Protection%20%F0%9F%9B%A1/00%20-%20Longevity%20%F0%9F%91%B4/Take%20Supplements.md)

[Take Pain Meds Midday](./Take%20Pain%20Meds%20Midday.md)


[Take ADHD Meds PM](./Take%20ADHD%20Meds%20PM.md)
[Take Pain Meds PM](./Take%20Pain%20Meds%20PM.md)

[Take Pain Meds Evening](./Take%20Pain%20Meds%20Evening.md)

[My Back Hurts](./My%20Back%20Hurts.md)

[Drink an Energy Drink](./Drink%20an%20Energy%20Drink.md)






### Inactive
[Meds for today are in the box](./Meds%20for%20today%20are%20in%20the%20box.md) 
[Adderall Withdrawal](./Adderall%20Withdrawal.md)
## Tasks




# Weekly
## Goals
## Tasks
[Fill Pill Caddy](./Fill%20Pill%20Caddy.md)

# Monthly
## Goals
[Pick up meds from CVS](../Pick%20up%20meds%20from%20CVS.md)

## Tasks
[Call the Doc to renew meds](../Call%20the%20Doc%20to%20renew%20meds.md)
[Verify CVS got my renewal](../Verify%20CVS%20got%20my%20renewal.md)


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
