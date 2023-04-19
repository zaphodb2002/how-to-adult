---
share: true
type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
spoonsStoredFromYesterday: 6
maxSpoonsStored: 90
spoonsGainedToday: 51
spoonsSpentToday: 44
spoonsPerDayBaseline: 36
maxSpoonsSpentPerDay: 90
---

#tool

## 🥄Current Spoons: `$= dv.current()["spoonsStoredFromYesterday"] + dv.current()["spoonsGainedToday"] - dv.current()["spoonsSpentToday"] ` / `$= dv.current()["maxSpoonsStored"]`🥄
### `$= (dv.current()["spoonsSpentToday"] / dv.current()["spoonsPerDayBaseline"](%22spoonsPerDayBaseline%22.md)) * 100`% min effort
### `$= (dv.current()["spoonsSpentToday"] / dv.current()["maxSpoonsSpentPerDay"](%22maxSpoonsSpentPerDay%22.md)) * 100`% max effort

# Things To Earn Spoons

[Life Management System](./00%20-%20Life%20Management%20System.md)
- Work the Maintenance Views for 30 minutes 🥄+5
- Work the Weekly Schedule 🥄+5

[Personal Wellness](./01%20-%20Personal%20Wellness.md)
- Stand up and stretch = 🥄+1
- Go outside = 🥄+1
- Have a snack = 🥄+2 (2x a day)
- Drink Coffee = 🥄+2 (2x a day)
- Drink an Energy Drink = 🥄+3 (1x a day)
- Meditate for 10 min = 🥄+5
- Dog time for 10 min = 🥄+5
- Refill my water = 🥄+10 (2x a day)
- Journal Entry = 🥄+10 (1x a day)

[Video Games](./03%20-%20Video%20Games.md)
- Play Video Games for 30 min = 🥄+5
- Play games with friends  = 🥄+25 (1x a day)

[Psychonautics](./04%20-%20Psychonautics.md)
- Have an edible = 🥄+30 (1x a day)

[Music](./05%20-%20Music.md)
- Listen to an album = 🥄+10

[Literature](./06%20-%20Literature.md)
- Read a chapter = 🥄+10

[Self Sufficiency](./07%20-%20Self%20Sufficiency.md)

[Animation](./08%20-%20Animation.md)
- Doodle for 30 min = 🥄+10

[Cinema](./09%20-%20Cinema.md)
- Watch an episode of Star Trek = 🥄+10 (1x a day)
- Watch a movie = 🥄+25 (1x a day)
- Watch a movie with friends 🥄+35 (1x a day)



# Notes
🥄1 = 5 minutes
maxSpoonsSpentPerDay is a hard cap.  Currently at 90 spoons, or 7.5 hours of work.  This may go up or down

#tool