---
share: true
type: "tool"
created: NaN 
modified: NaN
---
# Rolled Over From Yesterday
2023-04-18:: 6
2023-04-19:: 24
2023-04-20:: 9
2023-04-21:: 23
2023-04-22:: 13
2023-04-23:: 3
2023-04-24:: 39
2023-04-25:: 47
2023-04-26:: 50
2023-04-27:: -35
2023-04-28:: -2
2023-04-29:: 40
2023-04-30:: 73
2023-05-01::
2023-05-02::
2023-05-03::
2023-05-04::
2023-05-05:: 0
2023-05-06:: 18
2023-05-10:: 0
2023-05-11:: 6
2023-05-12:: 31
2023-05-13:: 40
2023-05-14:: 12
2023-05-15:: 42
2023-05-16:: 25
2023-05-17:: 24
2023-05-18:: 4
2023-05-19:: 0
2023-05-26:: 0
2023-05-27:: 0
2023-05-28:: 0
2023-05-29:: 11
2023-05-30:: -4
2023-05-31:: 6
2023-06-01:: 6
2023-06-02:: 0
2023-06-03:: -4
2023-06-04:: 0
# Gained Today
2023-04-18:: 62
2023-04-19:: 58
2023-04-20:: 57
2023-04-21:: 37
2023-04-22:: 57
2023-04-23:: 66
2023-04-24:: 39
2023-04-25:: 44
2023-04-26:: 26
2023-04-27:: 77
2023-04-28:: 117
2023-04-29:: 73
2023-04-30:: 
2023-05-01::
2023-05-02::
2023-05-03::
2023-05-04::
2023-05-05:: 40
2023-05-10:: 14
2023-05-11:: 73
2023-05-12:: 82
2023-05-13:: 25
2023-05-14:: 106
2023-05-15:: 39
2023-05-16:: 67
2023-05-17:: 41
2023-05-18:: 51
2023-05-28:: 49
2023-05-30:: 36
2023-05-31:: 35
2023-06-02:: 48
2023-06-03:: 59
# Spent Today
2023-04-18:: 44
2023-04-19:: 73
2023-04-20:: 42
2023-04-21:: 47
2023-04-22:: 67
2023-04-23:: 30
2023-04-24:: 31
2023-04-25:: 41
2023-04-26:: 111
2023-04-27:: 44
2023-04-28:: 75
2023-04-29:: 40
2023-04-30:: 
2023-05-01::
2023-05-02::
2023-05-03::
2023-05-04::
2023-05-05:: 28
2023-05-10:: 21
2023-05-11:: 48
2023-05-12:: 33
2023-05-13:: 40
2023-05-14:: 34
2023-05-15:: 30
2023-05-16:: 18
2023-05-17:: 57
2023-05-18:: 55
2023-05-28:: 27
2023-05-30:: 20
2023-05-31:: 29
2023-06-02:: 49
2023-06-03:: 45
#tool


referenceDateStart:: 2023-06-01
referenceDateEnd:: 2023-06-30
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
let current = spoonsGainedToday - spoonsSpentToday
dv.paragraph('Current: ' + current);


```