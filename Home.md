
---
cssclass: dashboard
banner: "![[Banner.gif]]"
banner_y: 0.494
banner_x: 0.5
---



---
<div class="title" style="color:Black">Notebook Dashboard</div>


# Vault Info

 - ✍️**Writing Projects**
	 ![[Dev Todo#^923f61 ]]
	 ![[Dev Todo#^776056]]


- 💰 Budget review
	- [[Q1 2024]]
	- [[Q2 2024]]
	- [[Q3 2024]]
	- [[Q4 2024]]


- 🔖 Tagged:  favorite 
 `$=dv.list(dv.pages('#favorite').sort(f=>f.file.name,"desc").limit(4).file.link)`
- 〽️ Stats
	-  File Count: `$=dv.pages().length`
	-  Personal recipes: `$=dv.pages('"Family/Recipes"').length`


# The List
- 💻 Dev Quest
	- [ ] [[Dev Roadmaps By Priority#Main Long Quest | Main Quest]]
	- [ ] [[Dev Roadmaps By Priority#New Path | New Path of Exploration]]
	- [ ] [[Dev Roadmaps By Priority#Side Quest Revist |  Side Quest]]

-  Top PDF
	-  [[BMA-SCHEDULE-7.1.2023.pdf]]


- 🗄️ Recent file updates
 `$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(11).file.link)`

- 🎥 Top to Watch
	- ![[Netflix watch]]

🎮 Top to Play
	![[Games]]


