---
Title: Remembrance Day (And US Thanksgiving) Development Update
Description: In this update we’re taking a look at some of the work being done on Infected behaviors, more weapons and animations, and some of the interactive sections players will face in the mines mentioned in previous updates. We also have a break down of some of the work that Nik Z, the lead developer, has been doing recently.
Author: Regicidalnut (RegiBless)
Date: 11/21/19
Template: post
---
# Remembrance Day/American Thanksgiving Development Update
Hey Survivors,
In honor of both Remembrance Day and Veteran's Day in the US last week, we honor the sacrifices and service of our armed forces. You will not be forgotten.




Before we get to the Dev Updates, this is a quick reminder, **anything shown on this blog and on the vlogs, is a work in progress** and is subject to change as development continues.


Want to be part of the conversation? Join our >>[Official Community Discord Server](http://discord.gg/deadmatter)<<




We're going to kick off the blog with an update from **Nik Z**, the Lead Developer of Dead Matter:
## Roadmap Update
Per our blog post in September, we mentioned that we would be addressing the state of the game in January as well as our plans for soft-launching our Closed Alpha. This is still the plan. We’ll be addressing this via a roadmap that will detail 2020 and beyond for Dead Matter. This requires us to put a lot of effort into planning out our production, but nonetheless we’re excited to deliver a very informal update come January.


What I can say at the moment is that we’re looking at having to change quite a few things on the game's backend as we will not be soft-launching onto Steam Early Access, but we will be using our own launcher. Our launcher will be much better for running a Closed Alpha, as we can easily gather player feedback, something we felt that Steam was far too restrictive and inefficient at handling. We’re also in the process of overhauling [QISoftware.ca](https://qisoftware.ca/) and we’ll be soon accepting hundreds of different payment methods, including PayPal.


We’re also potentially looking at working with a publisher to help maximize the quality and success of the project, this would be ideal for us especially before Steam Early Access. Rest assured knowing that we will not take any deal that compromises our artistic integrity or vision for the project.
## Programming Update
A lot of my work has been absent in these recent blog posts, and so I’ve decided to write up everything that I’ve been recently working on for people to get a sneak peak at some of the behind the scenes things going on in the project.


Please note that there may be some terminology used that you may be unfamiliar with.
## Networking Optimizations
Dead Matter is an extremely complex project, with tons of interactive elements. As a very basic example of this is that any light can be shot out, any light can also be turned on or off by a switch and lights are also an actor that requires power. One single apartment building in Dead Mans Flats contains hundreds of lights.


To simplify things, without the replication graph in place the server would have to iterate over every single light and determine if it should network the data to each player by comparing the players position to that of the light. This happens every single “tick” or “frame” on the server.


Our system combines the data being sent into a single actor that essentially acts as a data relay. This process is completely seamless for designers on the project working in Blueprint. On top of combining the data being sent we also compress it on the bit-level. For example, if you were to replicate a single light actor you would be sending at minimum 32 bits of data (replication overhead) plus for each byte or boolean you’re looking at sending an additional 8 bits of data.


With the way our system works, booleans and integers use the smallest possible amount of data. 1 bit for a Boolean, and 2-6 bits for a small integer. They’re packed into a blob and replicated from the server to clients. This results in significantly less data being sent over the wire and we’re also able to send partial updates, resulting in gains of up to 8x less data being sent from the server to the client.


I originally wrote the system for optimizing the interactive elements inside of buildings, such as lights. Since then, we’ve been able to add a lot of small networked interactions such as being able to pop tires on static vehicles.
<video autoplay loop muted>
 <source src="https://i.gyazo.com/4731db6a93cebde38ca73978a6428730.mp4" type="video/mp4" style="border:1px solid">
</video>
## Database Subsystem
Survival games require a persistent world, something Dead Matter lacked was a reliable way to save data to disk. I’ve written a Database subsystem for Unreal Engine 4 that uses our own Save Objects.


Binding data that needs to be saved is very painless for any of our programmers that work in C++. For anyone that has experience with Replication in Unreal Engine 4 this should look familiar to you.
<img src="https://i.imgur.com/KP5EOnu.png" align=”middle”>


I also added support for SQL Databases that will allow for a shared database across multiple servers, this means that you can play the same character on different servers. The system I wrote also has support for SQLite for singleplayer and for people that want to boot up a dedicated server with minimal hassle.


I’ve profiled the performance of the database and was able to process hundreds of queries per second. While I don’t anticipate Dead Matter ever needing to process that much data, we’ve definitely got the system needed to handle it.
## Inventory Overhaul
Our inventory system was the oldest code in our codebase, and it needed to be cleaned up a bit. We’ve converted all our Inventory Actors into Inventory Objects that are functionally identical. Most of the optimizations that our Inventory needed were put in place when we increased the grid density, but in order to get the most out of our Inventory system it was decided that converting them to Objects was a necessity.


Along with the Inventory changes, I’ve also been working on overhauling our item system. Our items are represented via a structure that contains the ItemID and any unique data that the item requires. I’ve also cleaned up the way that items are interacted with. Here is an example of a test item that I created.
<img src="https://i.imgur.com/Bpe1pMr.png" align=”middle”>


One big goal for me with the item overhaul was to increase the flexibility of ItemData and make it much easier to work with.


Originally ItemData was very restrictive and any data that didn’t fit into an integer or a float was saved as a string which is quite wasteful; this is no longer the case. Meaning that even less data gets sent over the wire and we’ve got an easier system to work with. Both a win-win. Only drawback is having to reprogram nearly every single item in the project, but that shouldn’t take long especially with the refined system in place.
## Weapons
Since our weapons were directly tied into our items, I’ve had to do a lot of surgery not only on the weapon system but the system that drives any item held in the players hands.


Our weapons are now a lot better than they were before and are easily 20x easier to work with, I’ve also been working on adding some procedural animation to them to try and reduce how stiff they look. Most of the weapon movement before these changes were introduced was animated by hand.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/RigidFancyCattle-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


One of the next steps I’ve yet to go through with the Weapons is implementing proper motion (that doesn’t stutter). I’m currently looking at implementing Simple Harmonic Motion as well as a critically dampened spring interpolation (for when aiming down sights). You can read about Simple Harmonic Motion here:


[http://digitalsalmon.co.uk/simple-harmonic-motion/](http://digitalsalmon.co.uk/simple-harmonic-motion/)


I’ve also finally been able to implement proper leaning animations, with the new procedural motion that’s been implemented this was an extremely easy and quick addition.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/NimbleHatefulIrishdraughthorse-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


We’ve had parallax scopes in the project for a while, but due to the way the aiming offsets were previously setup it was a nightmare to get them working consistently on every single weapon. So, I reworked that system with universal compatibility in mind.


<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/InsistentPeacefulBluewhale-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>
# Dev Updates
Anyone not mentioned has been working on things we’re not quite ready to talk about or show off at the time this blog was posted.


**Nomad** has been working on more gameplay elements for the mines that we have been highlighting in recent updates. To get around some of the obstacles in the mine, players will have to utilize the pump systems for gas and water hazards to clear a path that won’t kill them. *Please note that some sounds are placeholders or are missing, and that this is all a work in progress*.


<video autoplay loop muted>
 <source src="https://cdn.discordapp.com/attachments/626542398759108618/645075153717297182/2019-11-15_17-08-16.webm" type="video/mp4" style="border:1px solid">
</video>
Sound warning if unmuted , right click and show controls to unmute.


We want players to have to think and solve some form of puzzle to get through interesting or important areas so they aren’t just showing up, looking at a pretty room, looting it, then leaving.


<video autoplay loop muted>
 <source src="https://cdn.discordapp.com/attachments/626542398759108618/641839659923669004/2019-11-06_18-57-32.webm" type="video/mp4" style="border:1px solid">
</video>


**Abiscuits** has been continuing his work on vehicle systems in the game. He has started merging the new trailer mechanics into the main build of the game. The current attachment system is for testing purposes. As you can see in the clip below, trailers will obey the laws of physics, so players will need to mind their driving styles when hauling trailers.


<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/FearlessMilkyConch-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


Aside from the trailers, he has been working on ways to make static, non-driveable vehicles more interactive. Players will be able to shoot out the tires and eventually open, close, and blow the doors off of static vehicles. These aren’t mechanics that drastically affect gameplay, but they do a lot to make the world feel more alive and interactive.


<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/GloriousSophisticatedFlyingsquirrel-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


**Gunschlinger** has been working on more Infected behaviors, most recently their movement and horde grouping. For instance, two hordes responding to and moving towards a target together will merge into a single horde with a common goal.


<video autoplay loop muted>
 <source src="https://i.imgur.com/vc47cBy.mp4" type="video/mp4" style="border:1px solid">
</video>


<video autoplay loop muted>
 <source src="https://i.imgur.com/ATyVk8C.mp4" type="video/mp4" style="border:1px solid">
</video>


**Please note that the movement speed is not final. They are moving faster than intended in the clip above.**


**Stefan and Tac** have finished the 416 model and textures. Tac finished the model, and Stefan finished up the texturing. The 416 will be one of the rarer and more versatile weapon platforms available in the game.
<img src="https://i.imgur.com/HWDKKU6.jpg" align=”middle”>
<img src="https://i.imgur.com/lCmlD8W.jpg" align=”middle”>


**Rizzler** has this to write about his recent work:


>Hey everyone, The Rizzler here! For most props, regular modelling does the job to get the result you want to achieve, but sometimes you have to deal with “soft” objects, such as clothing, drapery and the like. This is when cloth simulation would be a better option to get a fast and high-quality result. My program of choice for such a task is Marvelous Designer.


>Here, I’ve gone back to a finished file and simply “pulled apart” the bag to show how the simulation runs - you can see the patterns wrapping around the inner pink static collision mesh;
<video autoplay loop muted>
 <source src="https://i.imgur.com/VawIs2W.mp4" type="video/mp4" style="border:1px solid">
</video>


>When creating the bag, I designed the parts in stages, simulating and layering parts on so I could more easily control the look and physics. I was then able to add more collision meshes in the form of loops and clips, allowing me to add more cloth side straps and a shoulder strap. It’s important to take it slow and in stages as cloth physics can be finicky. Here’s the finished bag in Marvelous. This will serve as the high poly mesh, which will be used to transfer detail onto the game-ready low poly mesh.
<img src="https://i.imgur.com/IAlZSPy.png" align=”middle”>


>This bag was created as part of a set of luggage with a texture masking system designed by Shirk to allow different colours for variation. I was also able to quite easily create some draped tarps over the piles using the exact same techniques I outlined above. Hope you enjoyed this actually-quite-technical look at cloth simulation based prop creation!


<img src="https://i.imgur.com/CIVM8Bv.png" align=”middle”>


Rizz has also been working on some of the other baggage and clothes that players are going to find on the ground throughout the Alberta. Clothes models found on the ground were created using a similar simulation as the canvas bag mentioned above.
<img src="https://i.imgur.com/nlbmYcs.png" align=”middle”>
<img src="https://i.imgur.com/bbfiapo.png" align=”middle”>


**Shiny Haxorus** has been busy lately finishing the texturing for the P90:
<img src="https://i.imgur.com/71oJGS3.png" align=”middle”>


He has also been working on reconfiguring the C7/8 to increase its modularity by adding various attachments and mounting points.
<img src="https://i.imgur.com/Xvu9BdT.png" align=”middle”>
<img src="https://i.imgur.com/caGPevm.png" align=”middle”>
<img src="https://i.imgur.com/yja4DTK.png" align=”middle”>


Along with the weapon texturing and modularity, Hax has started working on animations for some of the toolbelt items players will hold such as the compass. He'll also be working on animations for the SVD and some more vehicle animations moving forward.
<video autoplay loop muted>
 <source src="https://thumbs.gfycat.com/ColorfulPleasingAmericanwarmblood-mobile.mp4" type="video/mp4" style="border:1px solid">
</video>


**Regicidalnut**:


For my part, I have continued my work on various Points of Interest around the map, laying out the small stories and vignettes that they will find while exploring the world. I have also started work on NPC dialogue, notably with the voice actor for Duke Cartilage, the resident pirate radio broadcaster in Dead Matter's Alberta. He will inform players of incoming inclement weather, faction movements, and his own colorful take on the Canadian Apocalypse. Eventually he will also be a mission-giver NPC that players can choose to align with. The ultimate goal is for all interactive NPCs to be fully voiced and have dialog trees if players want to chat with them. Naturally, not *all* NPCs will be interactive.
<img src="https://i.imgur.com/Tep4Ulp.png" align=”middle”>


**Shirk** has been continuing his work on collision for buildings, level of detail meshes, doors, and the new lighting setup for buildings.
Most buildings will have 3 power states:


- Powered


- Emergency Power


- Off
<img src="https://i.imgur.com/MSYhCRc.png" align=”middle”>


Emergency powered buildings will only be lit by limited battery-powered lamps. The lights are sparse, and will offer minimal light inside buildings.
<img src="https://i.imgur.com/MsteQli.png" align=”middle”>


Of course, powered buildings will be fully illuminated and offer a bright and welcoming interior for players and Infected alike. Remember, the Infected are drawn to light and sound as well as seeing uninfected targets, so players will want to approach well-lit buildings cautiously.
<img src="https://i.imgur.com/UwzxSV1.png" align=”middle”>
<img src="https://i.imgur.com/e9VUnsb.png" align=”middle”>
<img src="https://i.imgur.com/Ic6Tvml.png" align=”middle”>


The improved lighting system allows for greater variation in light colors and differences in spaces both in and outdoors.
<img src="https://i.imgur.com/UI6LHyx.png" align=”middle”>
<img src="https://i.imgur.com/n15Eoyi.png" align=”middle”>
<img src="https://i.imgur.com/1IcooMu.png" align=”middle”>
<img src="https://i.imgur.com/N6Nldoq.png" align=”middle”>
<img src="https://i.imgur.com/SYAG1Gk.png" align=”middle”>
<img src="https://i.imgur.com/xItliQ7.png" align=”middle”>


**Alright everyone**. that wraps up this development update. Thank you all for your continued support, and we look forward to your feedback and chatting with you all.


If you're not a backer already and want to support the development of Dead Matter, you can back the project at the following links:


[IndieGogo](https://www.indiegogo.com/projects/dead-matter-pc-community#/)


or


[https://qisoftware.ca/store](https://qisoftware.ca/store)


Even if you can't, or aren't comfortable with backing just yet, spreading the word to your friends and talking about the game helps all the same.


Plan accordingly,


Regi