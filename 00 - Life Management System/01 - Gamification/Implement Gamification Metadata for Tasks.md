---
share: true
type: "quest"
sub-type: "minor"
status: "active"
created: NaN 
modified: NaN
---
 
 
# Things to Do

```dataviewjs
let tasks = dv.current().file.tasks
		.where(task => task.status == ' ');
//console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```
- [ ] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-03
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-03 ✅ 2023-08-08
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-03 ✅ 2023-08-03
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-02 ✅ 2023-08-03
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-02 ✅ 2023-08-02
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-02 ✅ 2023-08-02
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-02 ✅ 2023-08-02


# Goals
- [/] Convert Routine tasks to their own pages of type Entry #LMS 🆙+10 ➕ 2023-08-08 
- [/] Complete this Quest #LMS #bureaucracy  🆙+10 ➕ 2023-07-26 🛫 2023-07-26
# Summary
campaign::
aspect::
started:: 2023-07-26
completed::

## Complete Criteria:
1. 

## Why is this important?:

# Missions
1.

# Notes
## Goals Vs Tasks
### Tasks
- Tasks take 5 minutes or longer. 
- Tasks ALWAYS cost 🍅 and 🥄 (can be 0), and ALWAYS reward 🆙
- Tasks NEVER reward 🥄

### Goals
- Goals take effectively no time at all
- Goals are a statement of truth, yes or no.
- Goals may reward 🥄 and/or 🆙
- A good place for gratitude


## Player Resources
### Pomodoros 🍅
Represents the actual time required to complete a task.  🍅1 = 5 minutes.
#### Taps
- Flat amount per week
#### Sinks
- Completing Tasks
- Week ending


### Spoons 🥄
Represents the subjective energy required to complete a task.
#### Taps
- Meeting Goals
#### Sinks
- Completing Tasks


## Task Metadata
### Priority?

### Advantage Tags
#advantage/fun
#advantage/relaxing
#advantage/happy
#advantage/helpingOthers
#advantage/askingForHelp
#advantage/friends
#advantage/easy
#advantage/love
### Complication Tags
#complication/notFun
#complication/phoneCall
#complication/procrastination
#complication/tedious
#complication/depression
#complication/pain
#complication/axiety
#complication/adhd
#complication/difficult
#complication/gross
#complication/wet
### Time Cost
- 🍅 from estimates/timers
### Spoon Cost
- 🥄 = max(🍅  + sum(Comp) - sum(Adv), 0)
### Experience Gain
- 🆙 = 🍅 + 🥄

### Zone?
- #zone/workstation
- #zone/home
- #zone/garden
- #zone/neighborhood
- #zone/stephsHouse
- #zone/inTown
- #zone/ramona
- #zone/downTheHill
- #zone/temecula
- #zone/distantLands
# Things I've Done

```dataviewjs
let tasks = dv.current().file.tasks
		.where(task => task.status == 'x');
//console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```

- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-01 ✅ 2023-08-02
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-01 ✅ 2023-08-01
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-08-01 ✅ 2023-08-01
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 ✅ 2023-08-01
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-31 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-29 🛫 2023-07-31 ✅ 2023-07-31
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-29 🛫 2023-07-29 ✅ 2023-07-29
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-29 🛫 2023-07-29 ✅ 2023-07-29
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 🛫 2023-07-27 ✅ 2023-07-29
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 ✅ 2023-07-29
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 ✅ 2023-07-27
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 ✅ 2023-07-26
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 ✅ 2023-07-26
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 🛫 2023-07-26 ✅ 2023-07-26
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 🛫 2023-07-26 ✅ 2023-07-26
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 🛫 2023-07-26 ✅ 2023-07-26
- [x] Work on this for a pomodoro #LMS 🍅5 🥄5 🆙+10 ➕ 2023-07-26 🛫 2023-07-26 ✅ 2023-07-26