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
- [ ] Out of bed before 0700 #habit #depression 🥄+10
- [ ] Out of bed before 0800 #habit #depression 🥄+5
- [ ] Put pants on #habit #depression 🥄+5
- [ ] Put on shoes and socks #habit #depression 🥄+5
- [ ] Put on watch #habit #communication #BePrepared 🥄+5
- [ ] Worked for a full pomodoro loop #adhd #habit 🥄+5
# Weekly
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
