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

- [ ] Slept #sleep 🥄+5 🔺 
- [ ] Slept Well #sleep 🥄+5 🔺 

- [ ] Take Meds #habit #meds #adhd #hbp 🥄+5 🔺 
- [ ] Put on Glasses #habit #healthy #brain 🥄+2 🔺 
- [ ] Drink Water #habit #hydration 🥄+2 ⏫
- [ ] Refill my water #hydration 🥄2 🔼  
- [ ] Refill my water #hydration 🥄2 🔼 
- [ ] Take 2nd Adderall (optional) #habit #meds #adhd  🥄+5 ⏫
- [ ] Drink Water #habit #hydration 🥄+2 ⏫
- [ ] Drink Water #habit #hydration 🥄+2 ⏫



# Weekly
# Monthly
- [ ] Call the Doc to renew meds #PhoneCall #NotFun #adhd 🥄10 🔺 
- [ ] Verify CVS got my renewal #adhd 🥄5 🔺 
- [ ] Pick up meds from CVS #NotFun #adhd #DownTheHill 🥄20 🔺
# Seasonally
- [ ] Make a doc appt #PhoneCall #NotFun #healthy #adhd #meds #hbp 🥄10 🔺 
- [ ] Make a dental appt #PhoneCall #NotFun #healthy #adhd #grooming #hygiene 🥄10 🔺 
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
