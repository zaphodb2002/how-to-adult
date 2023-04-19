---
share: true
type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---
# Campaigns
## Campaigns with invalid metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "campaign")
.where(page => page["alias"] == undefined);


let result = "";
for (let page of pages)
{
	result += page.file.link + '\n';
}
dv.el("div", result);
```
# Aspects
## Aspects with invalid metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "aspect")
.where(
	page => page["campaign"] == undefined
	|| typeof(page["campaign"]) == 'string'
	  );

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "campaign: " + page["campaign"] + '\n\n';
	
}
dv.el("div", result);
```

# Quests
## Quest status
### Main Quests
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "main");

for (let page of pages)
{
	result += '- ' + page.file.link + ": " + page["status"] + ' for ' + page["campaign"] + '\n';
}
    
dv.el("div", result)
```
### Active Quests
```dataviewjs
let result = "";
let pages = dv.pages('#active')
    .where(page => page["type"] == "quest");

for (let page of pages)
{
	if(page["status"] == "active")
		result += '- ' + page.file.link + ": " + page["status"] + ' for ' + page["campaign"] + '\n';
}
    
dv.el("div", result)
```


### Available Quests
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");

for (let page of pages)
{
	if(page["status"] == "available")
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"campaign"]('%20+%20page%22campaign%22.md)\n';
}
    
dv.el("div", result)
```

## Quests with no missions
NOT YET IMPLEMENTED
## Undocumented Quests
```dataviewjs

function write(message)
{
    return message + "\n";
}

function bullet(message)
{
    return "- " + write(message);
}

function header(message, size)
{
    let hashes = "";
    for(let i = 0; i < size; i++)
    {
        hashes += "#";
    }
    return hashes + " " + write(message);
}


let questsWithNoAspectResult = "";

let pages = dv.pages()
    .where(page => page["type"] == "quest");

for(let page of pages)
{
    let aspectConnected = false;
    let inlinks = page.file.inlinks;
    for(let inlink of inlinks)
    {
        let inlinkPage = dv.page(inlink);
        if(inlinkPage.file.frontmatter["type"] == "aspect")
        {
            aspectConnected = true;
        }
    }
    if(!aspectConnected)
    {
        questsWithNoAspectResult += bullet(page.file.link)
    }
    
    
}
dv.el("div", questsWithNoAspectResult)
```

## Quests with invalid metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "quest")
.where(
	page => page["sub-type"] == undefined
	  || page["campaign"] == undefined
	  || page["campaign"] == ""
	  || typeof(page["campaign"]) == 'string'
	  );

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "campaign: " + page["campaign"]  + '\n';
	result += "aspect: " + page["aspect"] + "\n";
	result += "status: " + page["status"] + '\n\n';
	
}
dv.el("div", result);
```

# Missions
## Mission Status
```dataviewjs
function write(message)
{
    return message + "\n";
}

function bullet(message)
{
    return "- " + write(message);
}

function header(message, size)
{
    let hashes = "";
    for(let i = 0; i < size; i++)
    {
        hashes += "#";
    }
    return hashes + " " + write(message);
}

let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "mission");

for (let page of pages)
{
	result += bullet(page.file.link + ": " + page["status"] + ", for [" + page"quest"](%22%20+%20page%22quest%22.md)');
}
    
dv.el("div", result)
```

## Missions with no Quest
```dataviewjs

function write(message)
{
    return message + "\n";
}

function bullet(message)
{
    return "- " + write(message);
}

function header(message, size)
{
    let hashes = "";
    for(let i = 0; i < size; i++)
    {
        hashes += "#";
    }
    return hashes + " " + write(message);
}


let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "mission");

for (let page of pages)
{
	if(page["quest"] == "FILL THIS OUT" || page["quest"] === undefined)
	{
		result += bullet(page.file.link);
	}
}
    
dv.el("div", result)
```
## Missions with no active tasks
NOT YET IMPLEMENTED
## Undocumented Missions
```dataviewjs

function write(message)
{
    return message + "\n";
}

function bullet(message)
{
    return "- " + write(message);
}

function header(message, size)
{
    let hashes = "";
    for(let i = 0; i < size; i++)
    {
        hashes += "#";
    }
    return hashes + " " + write(message);
}


let missionNoQuestResult = "";
let pages = dv.pages()
    .where(page => page["type"] == "mission");

for(let page of pages)
{
    let link = bullet(page.file.link);
    let inlinks = page.file.inlinks;
    let questConnected = false;
    for (let inlink of inlinks)
    {
        let inlinkPage = dv.page(inlink);
        if (inlinkPage.file.frontmatter["type"] == "quest")
        {
            questConnected = true;
        }
        
    }

    if(!questConnected)
        missionNoQuestResult += link;
    
}
dv.el("div", missionNoQuestResult)
```

## Active Missions with Inactive Quests
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "mission")
    .where(page => page["status"] == "active");

for(let page of pages)
{
    let quest = page["quest"];
    let questIsActive = false;
    if(quest != undefined)
    {
	    let questPage = dv.pages().where(page => page.file.name == quest);
	    if(questPage["status"].values[0] != "active")
		    result += page.file.link += '\n'; 

    }
}
dv.el("div", result)
``` 
## Missions with invalid metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "mission")
.where(page => page["status"] == undefined);

let result = "";
for (let page of pages)
{
	result += page.file.link + '\n';
}
dv.el("div", result);
```
# Routines
## Routines with invalid Metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "routine")
.where(
	page => page["status"] == undefined
	  );

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "status: " + page["status"] + '\n\n';
	
}
dv.el("div", result);
```
# Tasks
## Top 20 Unscheduled Tasks
```tasks
limit 20
path does not include Routine
path does not include Daily
path does not include Shopping
show urgency
not done
no start date
no scheduled date
no due date

short mode
```
## Tasks completed today
```tasks
done today
short mode
```
## Tasks with no tags
```tasks
no tag
limit 20
not done
```

## Tasks scheduled in the past
```tasks
scheduled before today
not done
limit 20
```

## Tasks with invalid Metadata
```tasks
description does not include 🥄
not done

```
# Notes
## Notes that Don't Exist
```dataviewjs
const pages = dv.pages()
.where(page => page.file.outlinks.length > 0);
let result = "";

for (let page of pages)
{
	
	for (let link of page.file.outlinks)
	{
		if(dv.page(link) == undefined)
			result += page.file.link + ': ' + link + '\n';
	}
}

dv.el("div", result);
```
## Notes with No Content
```dataviewjs
const pages = dv.pages().where(page => page.file.size < 50)

dv.list(pages.file.link)
```
## Notes with no Tag
```dataviewjs
const pages = dv.pages().where(page => page.file.tags.length == 0);
let result = "";
for (let page of pages)
{
	result += page.file.link + '\n';
}
dv.el("div", result);
```
## Notes with No Links
```dataviewjs
const pages = dv.pages()
.where(page => page.file.inlinks.length == 0)
.where(page => page.file.outlinks.length == 0);
let result = "";
for (let page of pages)
{
	result += page.file.link + '\n';
}
dv.el("div", result);
```
## Notes with Invalid Metadata
```dataviewjs
const pages = dv.pages()
.where(
	page => page["share"] == undefined
	|| page["type"] == undefined
	  )
.where(page => !page.file.path.includes("Template"));

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "share: " + page["share"]  + '\n';
	result += "type: " + page["type"] + '\n';
	result += '\n';
	
	
}
dv.el("div", result);
```

#tool