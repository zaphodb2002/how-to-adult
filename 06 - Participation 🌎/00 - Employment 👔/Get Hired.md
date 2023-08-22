---
share: true
type: "mission"
status: "active"

created: NaN 
modified: NaN
---
 
# Summary
quest:: [Find Employment](./Find%20Employment.md)
started:: [2023-04-26](../../00%20-%20Life%20Management%20System/09%20-%20Daily%20Notes/2023-04-26.md)
completed::
# Tasks
- [x] Interview with Complia Health #NotFun #PhoneCall #work 🥄15 ⏫ ⏳ 2023-06-06 📅 2023-06-06 ✅ 2023-06-06
- [ ] Do the Thing 🍅1 🥄1 🆙+2 ⏫ ➕ 2023-04-26 🛫 2024-04-26
- [x] Email Nan to follow up on the Complia Health thing #work #communication 🥄3 🆙+3 ➕ 2023-06-19 ✅ 2023-06-19
# Notes
2023-06-06 - Interview with Complia Health today


2023-05-11 - Etrailer.com is a bust. They chose someone else.


Got an interview with Etrailers.com.

13:27 It is now half an hour after my scheduled interview time and no one has shown up. Kevin is not answering his phone. I called their sales line and spoke to Kim who says she spoke to the HR dept. She took my number and said someone would call me right away. If I do not get a call in the next 5 minutes or so, I will call Kevin again. This is honestly pretty shitty, they're wasting a lot of my time.

13:43 called the sales people again. Josh this time. He's trying to get me to someone in HR. Kevin still not picking up his phone. Meeting has timed out. Clearly no respect for my time. Not getting off the phone until I get to somebody who can tell me why this happened.

I did finally get hold of Kevin, basically Josh just physically went and found him. Turns out Kevin doesn't know how to work his email and failed to cancel the meeting without calling me or confirming that I had accepted the change or something. I now have to reschedule, which is a huge hassle because Steph both wants to buy a car and also deliver her Jeep to the mechanic tomorrow, and Friday is my cleaning day with Mom and that's already mega stressful. I am incredibly [Frustrated](Frustrated.md) with this situation.

## Facts About the company
- HR Contact is Kevin Tiernan (kevin.tiernan@etrailer.com)
- Salary Range is 100K to 140K - Ask for 140K
- Web based retail website is product
- Based in MO, will have to go out there a few times a year
- Company promotes internally and employs its own devs which is awesome
- Good reviews from previous employees
- Good reviews from customers on Reddit
- Good responses on BBB complaints and very few of them
- TJ Bross is President and Founder, looks like. Not a shitbag from what I can tell. At least one left leaning comment on Twitter and mostly ads and grind mentality shit. Also bicycling apparently.

## Questions
- What's the tech stack like?
- Developer SQL API (ORM like Entity Framework / Dapper or ADO.NET / ODBC)
- SQL Server Infrastructure and configuration (SQL Server versions and number of servers, number and size of databases, Replication, Always On, etc)
- Azure, on-prem, or managed?
- Who's been managing it in the past?
- Pain points?
- 

## Things about me worth mentioning
- 
- General programming/scripting competence
	- C#
	- Git
	- Powershell
	- Bash
	- Javascript
	- Python
	- C++
- Brent Ozar (Microsoft Certified Master) training
- Pinal Dave (SQLAuthority.com) training
- Red Gate tool familiarity
- SentryOne tool familiarity
- Performance junkie, fast cars, overclocking, game and simulation engine performance
- Obsession with learning new things and mastery over systems, autodidact
- Outside of work
	- Game Design and Development
	- Engineering and Design
	- Dogs and Hiking
	 - Psychology, Philosophy, and Political Science (Social Sciences)
	 - Botany and Horticulture
	- Film and Animation
	- Musician

## SQL Server gotchas and things I never remember the name of

Window functions (OVER) - row counts and shit, calculations at the row level, as opposed to aggregate functions like SUM(). Shows every row.
- Lead and Lag - Lead gives rows after the current row you're getting, lag gives rows before the value.
- uses Partition By, which is like group by but for window functions

Coalesce() - get the first non-null result in a list

Union vs Union All - union all has dupes

HAVING - A where for grouping results (eg, thing, COUNT(thing) From table GROUP BY thing Having COUNT(thing) >= 2 would find things that are duplicates)

INNER vs LEFT joins - inner gives things that contains values for both rows, left gives everything from the left side and leaves nulls in unmatched rows on the right.

## My Process
1. Check Wait Stats for core issue (watch for duration of stats, reboots flush it)
	1. ASYNC_NETWORK_IO - talk to network or storage engineers
	2. CXPACKET - Parallelization issues. Check best practices on config and look for parameter sniffing or lopsided queries (lots of execution plans)
	3. LCK or PAGELATCH - Concurrency and/or cache junk issues
	4. PAGEIOLATCH - Expensive or very rarely run read queries
	5. SOS_SCHEDULER_YIELD - CPU pressure. often due to ad hoc queries and lack of cached execution plans.
	6. WRITELOG - Expensive write queries
2. General assessment of best practices and hardware
3. Execution plan analysis
4. Index tuning
5. Query tuning
6. Query refactoring
7. Software refactoring


# Things I've Done

- [x] Job interview with etrailer.com people @ 0900 (on the calendar) #work #interview #anxiety 🥄30 ⏫ ➕ 2023-04-26 🛫 2023-04-27 ⏳ 2023-04-27 📅 2023-04-27 ✅ 2023-04-27
- [x] Reschedule with Kevin 🥄5 🆙+5 ⏫ ➕ 2023-04-26 🛫 2023-04-26 ⏳ 2023-04-26 📅 2023-04-26 ✅ 2023-04-26
- [x] Get ghosted at a Job interview with etrailer.com people @ 1300 (on the calendar) #work #interview #anxiety 🥄30 ⏫ ➕ 2023-04-25 🛫 2023-04-26 ⏳ 2023-04-26 📅 2023-04-26 ✅ 2023-04-26
- [x] Set up the laptop so I can have a webcam #tinkering 🥄10 🆙+10 ⏫ ➕ 2023-04-26 🛫 2023-04-26 ⏳ 2023-04-26 📅 2023-04-26 ✅ 2023-04-26
- [x] Prepare for the interview #BePrepared #anxiety 🥄10 🆙+10 ⏫ ➕ 2023-04-26 🛫 2023-04-26 ⏳ 2023-04-26 📅 2023-04-26 ✅ 2023-04-26
- [x] Research Etrailers.com #BePrepared 🥄2 🆙+2 ⏫ ➕ 2023-04-26 🛫 2023-04-26 ⏳ 2023-04-26 📅 2023-04-26 ✅ 2023-04-26