---
Title: Happy Holidays Development Update
Description: In this update we’re taking a look at developements that have been made on the closed alpha map, the new snow effects (and snow deformation!), road signs for Canmore, and hearing from some of the new devs on the team!
Author: Regicidalnut (RegiBless)
Date: 31 December 2019
Template: post
---
# Happy Holidays Development Update
Hey Survivors,


From all of us at QIS, we wish you all happy holidays, and a happy New Year!


2019 has been a wild ride, and we want to thank you all for being here with us and supporting Dead Matter. This year our [Discord Server](http://discord.gg/deadmatter) community has nearly doubled from 10,606 members, to *21,110* when this was written. The community is growing everyday, and we can't thank you all enough for your continued support.


We got our Instagram account up and running! Check it out >[Here](https://www.instagram.com/playdeadmatter/)<

The team has also grown to 19! We now have 6 programmers, 10 artists, and 3 animators working to bring the best Dead Matter to players (and that is wildly oversimplifying the amazing work they're doing). I'm looking foward to working with them to show off what they've been working on when they're ready to be posted on the blog and in future vlogs.


Before we get to the Dev Updates, this is a quick reminder, **anything shown on this blog and on the vlogs, is a work in progress** and is subject to change as development continues.
## Dev Updates!
Anyone not mentioned has been working on things we’re not quite ready to talk about or show off at the time this blog was posted.
###**Hippowombat**
(one of our new artists)
>I've started working on dynamic weather functions for Dead Matter, beginning with dynamic snow. The first step was to set up a base layer that faded snow visuals and displacement based on a combination of elevation (snow level dropping with temperature) and angular allowance, which cooperatively drive each other as the global snow coverage value increases in-game.
<video autoplay loop muted>
 <source src="https://i.imgur.com/Eqwe0cw.mp4" type="video/mp4" style="border:1px solid">
</video>
>Next I wanted to make sure that coverage didn't occur under covered areas, so I built out a system that lets the level designers bake out a static intersection map for static objects. With texture packing we should be able to cover a massive area (100km²) with reasonable intersection accuracy.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/GiftedHandmadeBlackfly-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


>Looking at how snow builds in real life, I added an additional pass to allow snow to pile up against objects that it intersects with.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/ImperfectHelpfulCaracal-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>
>Finally, I began work on a dynamic pass that allows for snow trails/indentation in-game, by capturing select actors and writing them to a temporary buffer that travels with the player.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/MagnificentBriefGalapagoshawk-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>
>From here, I'll be focusing on refining the static capture process to make sure it's as efficient & easy to use as possible, and then I'll be looking at ways to keep dynamic snow trails persistent even if the player isn't around when they're created, or if they leave the area where they're created.


### Nihito
(another of our new artists)


Nihito has been working on signage that players will find throughout the Canmore area of the closed alpha map. Our players that live in, or have been to, the Canmore area in real life will feel right at home during the apocalypse. Hopefully the place you're looking for isn't overrun by the Infected.
<img src="https://cdn.discordapp.com/attachments/653056344177508392/653057442720120851/HighresScreenshot00003.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/653056344177508392/653057390794768384/HighresScreenshot00005.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/653056344177508392/653057400860835881/HighresScreenshot00006.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/653056344177508392/653057435170504735/HighresScreenshot00007.jpg" align=”middle”>


### Disseminate
(one of our new programmers)
>I've been getting up to speed with the project and what's been done already (and there's a lot that's been done already so it's taking a while to get used to where everything is!)


>For now, I've mostly been working on Dead Matter's user interface. Specifically, creating a window manager, building input components, and doing a pass on the main menu. If you're not super technically inclined, a window manager keeps track of the UI windows that are open, has some utilities for making new windows like prompts or the server browser, etc. Generally nothing too flashy, but getting this done means we can whip up UI in no time. This is useful for stuff like panels on machinery, equipment, ingame interactable stuff.


>I've been tweaking the settings/options menu as well. We want to make sure nobody playing Dead Matter suffers bad performance for any reason, so we need to take care with the settings we implement. I also worked on the server browser a bit to make it more performant.


>For something more interesting, I've been planning the timeline, seasons, and weather systems in Dead Matter. One of our goals is to make a realistic timeline as you play; the world should change with time and there shouldn't be any hiccups, inconsistencies, or generally weird bugs (for example, a jittery sun/sky, or snow in July). It's still in the planning phase but I think it's coming along smoothly.


### Regicidalnut


I'm still working on dialog for Duke Cartilage (maybe I'll get to post some samples in the future). I've also been working on fleshing out some of the characters players will be interacting with later on in development. I want the NPCs players interact with on a regular basis to have believable backgrounds and situations to talk about and possibly explore in the world (if you're feeling up to that).


**Alright everyone**. that wraps up this development update. Thank you all for your continued support, and we look forward to your feedback and chatting with you all. Keep an eye out for our Roadmap update coming out next month that will have some important information regarding the closed alpha.


If you're not a backer already and want to support the development of Dead Matter, you can back the project at the following links:


[IndieGogo](https://www.indiegogo.com/projects/dead-matter-pc-community#/)


or


[https://qisoftware.ca/store](https://qisoftware.ca/store)


Even if you can't, or aren't comfortable with backing just yet, spreading the word to your friends and talking about the game helps all the same.


See you all (very clearly) in 2020!


Plan accordingly,


Regi