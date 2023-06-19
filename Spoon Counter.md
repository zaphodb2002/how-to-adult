---
share: true
type: "tool"
created: NaN 
modified: NaN

maxSpoonsStored: 90
spoonsPerDayBaseline: 36
maxSpoonsSpentPerDay: 90
referenceDateStart: 2023-06-01
referenceDateEnd: 2023-06-30
---

#tool
```dataviewjs
let spoonChar = '🥄';
let today = new Date();
let yesterday = new Date();
yesterday.setDate(yesterday.getDate() - 1);
today = today.toISOString().split("T")[0];
yesterday = yesterday.toISOString().split("T")[0];
let referenceDate = today;

dv.paragraph(referenceDate)
let tasks = dv.pages().file.tasks
	.where(task => new Date(task.completion) >= new Date(referenceDate))
	.where(task => task.text.includes(spoonChar));
//dv.list(tasks)	

let spoonsGainedToday = 0;
let spoonsSpentToday = 0;

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

	if(isNaN(spoonsValue))
	{
		continue;
	}
	
	if(givesSpoons)
	{
		spoonsGainedToday += spoonsValue;
	}		
	else
	{
		spoonsSpentToday += spoonsValue;
	}
	//dv.paragraph(task.text)
	
}

dv.paragraph('+' + spoonsGainedToday);
dv.paragraph('-' + spoonsSpentToday);
let minEffort = (spoonsSpentToday / dv.current()["spoonsPerDayBaseline"]) *100

let maxEffort = (spoonsSpentToday / dv.current()["maxSpoonsSpentPerDay"]) *100 


dv.paragraph( minEffort + "% min effort")
dv.paragraph(maxEffort + "% max effort")
```


```dataviewjs
let spoonChar = '🥄';
let page = dv.current();
let referenceDateStart = dv.current()["referenceDateStart"];
let referenceDateEnd = dv.current()["referenceDateEnd"];

let tasks = dv.pages().file.tasks
	.where(task => task.completion >= referenceDateStart)
	.where(task => task.completion <= referenceDateEnd)
	.where(task => task.text.includes(spoonChar));	

let spoonsGainedToday = 0;
let spoonsSpentToday = 0;

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
	if(isNaN(spoonsValue))
	{
		continue;
	}
	if(givesSpoons)
	{
		spoonsGainedToday += spoonsValue;
	}		
	else
	{
		spoonsSpentToday += spoonsValue;
	}
	//dv.paragraph(task.text)
	
}

dv.paragraph('+' + spoonsGainedToday);
dv.paragraph('-' + spoonsSpentToday);
let current =  spoonsGainedToday - spoonsSpentToday


dv.paragraph('## 🥄Current Spoons: ' + current + "/" + dv.current()["maxSpoonsStored"]+"🥄");
```


# Things To Earn/Spend Spoons

## [Life Management System](./00%20-%20Life%20Management%20System.md)
---
- Work the Maintenance Views for 30 minutes #bureaucracy #sorting  🥄5
- Work the Weekly Schedule #bureaucracy #sorting  🥄5

## [Personal Wellness](./01%20-%20Personal%20Wellness.md)
---
- Stand up and stretch #exercise #healthy 🥄+1
- Spend time outside #outside #healthy  🥄+1
- Walk in the Garden #outside #garden #healthy #fun 🥄+2
- Go for a walk #exercise #outside #healthy  🥄+5
---
- Start Laundry #tidying  #clothes 🥄2
- Start Drier #tidying #clothes 🥄2
- Put away clothes #tidying #clothes  🥄5
---
- Have a snack #Food  🥄+1 (2x a day)
- Drink Coffee #caffeine #adhd  🥄+2 (2x a day)
- Refill my water #hydration 🥄+2 (2x a day)
- Drink an Energy Drink #caffeine #adhd  🥄+3 (1x a day)
- Prep a meal #cooking #Food  🥄+5
---
- Meditate for 10 min #mindfulness #adhd  🥄+2
- Dog time for 10 min #happy #fun 🥄+2
- Journal Entry #mindfulness #writing 🥄+5 (1x a day)
---
- Listen to an episode of [Spout Lore](Spout%20Lore.md) #podcast #fun #PtbA #ttrpg #comedy 🥄+2
- Watch 30 minutes of YouTube 🥄+5
- Listen to an episode of [No Dogs in Space](No%20Dogs%20in%20Space.md) #podcast #fun #music #lpotl #history 🥄+2 
---
- Good Mood #cyclothymia #adhd #fun #happy 🥄+5
- Nice Weather #environment #happy 🥄+2
- Yucky Weather #environment #unhappy 🥄2
- Bad Mood #cyclothymia #adhd #NotFun #unhappy  🥄5
- Adderall Withdrawal #adhd #NotFun 🥄5
---
- My back hurts #pain #myBack #old 🥄10
- Take pain meds #NSAIDsToTheRescue #pain #old 🥄+5
---
- Tidy [Bedroom](./Bedroom.md) for 15 minutes #tidying #myHouse 🥄5
- Put sheets on bed #tidying #sleep 🥄5
---
- Spend Time With Friends #socializing #happy #fun 🥄+5
---
- Go to Steph's #StephsHouse 🥄5
- Go into Town #InTown 🥄10
- Drive down the hill and back #DownTheHill  🥄20
- Drive to Temecula and back #temecula 🥄30
---
- Steph's Doc Appt #NotFun #DownTheHill 🥄15
- Grocery Shopping #Food #shopping #money 🥄10
- Home Depot #shopping #fun 🥄5

## [Video Games](./03%20-%20Video%20Games.md)
---
- Play Video Games for 30 min #fun 🥄+5
- Play games with friends  #fun #socializing  🥄+10

## [Psychonautics](./04%20-%20Psychonautics.md)
---
- Have an edible #420BlazeIt  🥄+15
- Clean Weed Stuff #cleaning  🥄+5

## [Music](./05%20-%20Music.md)
---
- Listen to an album #music 🥄+6
- Listen to playlists for new music #music 🥄+2
- Play bass for 30 minutes #music #bass #practice #fun 🥄+6

## [Literature](./06%20-%20Literature.md)
---
- Read a chapter #reading 🥄+10

## [Self Sufficiency](./07%20-%20Self%20Sufficiency.md)
---

- Water the Garden #outside #garden #myHouse 🥄5
- Pull Weeds #outside #garden #myHouse #exercise 🥄5
- Weedwhack #outside #myHouse #exercise  🥄10
- Mow the Lawn #outside #myHouse #exercise 🥄10

## [Animation](./08%20-%20Animation.md)
---
- Fill a sketchbook page #art 🥄+5

## [Cinema](./09%20-%20Cinema.md)
---
- Watch an episode of Star Trek #StarTrek #DS9 #WorfSux 🥄+10 
- Watch a movie 🥄+25 (1x a day)
- Watch a movie with friends 🥄+35 (1x a day)



# Notes
---
🥄1 = ~5 minutes
maxSpoonsSpentPerDay is a hard cap.  Currently at 90 spoons, or 7.5 hours of work.  This may go up or down


[Spoon Tracker](./Spoon%20Tracker.md)
#tool