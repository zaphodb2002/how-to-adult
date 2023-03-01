```dataviewjs

let debug = true;

let today = new Date();
let todayClean = CleanDate(today);
let cutoffDate = CleanDate(new Date());
cutoffDate.setDate(cutoffDate.getDate() + 7);

let _quests = dv.pages("#quest");

let preparedSets = []

for (let quest of _quests)
{
	if(quest.file.folder.endsWith("Templates"))
	{
		continue;
	}
	let missions = []
	for (let mission of quest.file.outlinks)
	{
		missions.push(mission = dv.page(mission).file);
	}

	let newSet = {
		quest: quest.file.link,
		missions: missions
	};
	preparedSets.push(newSet);
}

Display();


//---------------------------------------------------------

function Display()
{
	for (let set of preparedSets)
	{
		dv.el("li",dv.el("b",set["quest"]));
		for(let mission of set.missions)
		{
			if(mission.folder.endsWith("System"))
			{
				continue;
			}
			dv.el("li",mission.link);

			for(let task of mission.tasks)
			{
				if(task.due < cutoffDate)
				{
					dv.el("li",task.text);
				}
				
			}
		}
	}
	dv.el("p", "Showing tasks due until "+cutoffDate.toLocaleString());
}

function CleanDate(date)
{
	date.setHours(0);
	date.setMinutes(0);
	date.setSeconds(0);
	date.setMilliseconds(0);
	return date;
}

function Log(message)
{
	if(debug)
	{
		dv.el("p", dv.el("code", message));
	}
	
}


```
