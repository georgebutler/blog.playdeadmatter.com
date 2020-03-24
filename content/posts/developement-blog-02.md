---
Title: September Development Update
Description: Here is the first of many blog posts between the vlogs. In this post we’ll touch on some community matters like the forums, go over what the devs have been doing lately, and get a deep dive on what Shirk has been doing in the last couple weeks. These blog posts offer us a chance to dig further into the technical aspects of development and allow us to show off in the vlogs. Fair warning, there are some large images and gifs within the blog that may impact mobile data users.
Author: Regicidalnut (RegiBless)
Date: 09/25/19
Template: post
---
# September Development Update
Hey Survivors,


Welcome to the first of many blog posts showing progress on the game and what the devs have been up to since the most recent vlog. These blog posts will offer the team a chance to share their recent work and dig into the technical aspects of what they’re doing. Things that generally wouldn’t be shown in the vlog because of their length or format. I hope you enjoy this and the rest of them moving forward!


First things first, we stated in the last blog that we are going to be more transparent and communicative moving forward. Bearing that in mind, we’re going to be reviewing the state of the game again in January to make a determination on whether or not we feel we can make the March 2020 estimation. If it is determined that we need to push the closed alpha back again, we will make an announcement at that time. We don’t want to string anyone along by getting close to the deadline again and breaking the news that the game isn’t where we want it to be. We want to be as open as possible so people have better expectations in the future.


As a quick reminder, **anything shown on this blog and on the vlogs, is a work in progress** and is subject to change as development continues.


Last week most of the development team and some of the moderators did some playtests to check network performance and the new vehicle systems shown in [Vlog 09](https://youtu.be/ue_vkZA3GFQ?t=104). We also have the tools setup within Steam for anyone with a copy of the game to launch and maintain their own Dead Matter dedicated servers from within Steam. Players will be able to either host one locally just for themselves or others on their network, or use the same files to host dedicated servers as they wish.
The test highlighted some bugs and performance issues that needed to be addressed across all aspects of development before being ready to show off. The team had a great time during the test, though, and the in-game VoIP system works with incredible clarity. There is even a filter for the chatter that will eventually happen via the walkie-talkies in-game.
The current multiplayer test map is a single tile copied from the main map, and testing will remain on this test map until the rest of the world is more developed. Ideally, improving this testing mean more footage from future multiplayer tests can be shown.
<img src="https://i.imgur.com/DyBVf9Q.png" align=”middle” style="border:1px solid">
[High Resolution Link](https://cdn.discordapp.com/attachments/590051070324244501/626185799326760961/CurrentTestArea.png) - Fair warning, this is a massive image.
<img src="https://i.imgur.com/ScQudkz.png" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/AxTH37c.png" align=”middle” style="border:1px solid">
### Dev Updates:
Anyone not mentioned has been working on things we’re not quite ready to talk about or show off at the time this blog was posted.




**Gunschlinger** has been working on implementing some of Sully’s new animations to the Infected AI. They will now find something smashing to do, or have a lie down, until they set their eyes (or ears) on a target to attack. The other animations shown in the vlog will be implemented as time goes on.
Zombies will spawn into the map and dynamically find places to lean against the walls or lay down (an animation on the list to be implemented). Gunschlinger achieved this by writing a custom EQS (Environmental Query System) that makes the zombies try to find certain points that are near walls. Then they check the height of that point to find a good location to lean on. Zombie perception will rotate according to their head, so players will be able to sneak around a zombie leaning against a wall if they are quiet enough.
<video autoplay loop muted>
  <source src="https://i.imgur.com/bcoU3Ye.mp4" type="video/mp4" style="border:1px solid">
</video>
Zombie head smash implementation by Gunschlinger and Sully (animator)




**Rizzler** has been working on the M14, which has since been textured by Stefan.
[Rizzler’s Artstation](https://www.artstation.com/artwork/W2V31y)
<img src="https://cdn.discordapp.com/attachments/339047556430561282/623884904127791116/M14-Presentation-standard.jpg" align=”middle” style="border:1px solid">
<img src="https://cdn.discordapp.com/attachments/624391996265594880/626095176384774149/M14-Presentation-M2A.jpg" align=”middle” style="border:1px solid">
<img src="https://cdn.discordapp.com/attachments/624391996265594880/626095174887538699/M14-Presentation-SOCOM.jpg" align=”middle” style="border:1px solid">
<img src="https://cdn.discordapp.com/attachments/624391996265594880/626095181753614366/M14-Presentation-EBR.jpg" align=”middle” style="border:1px solid">
<img src="https://cdn.discordapp.com/attachments/624391996265594880/626095179203346432/M14-Presentation-Archangel.jpg" align=”middle” style="border:1px solid">




**Stefan** has finished texturing the M14 and is in the process of modelling another Backer Weapon: the Dragunov sniper rifle. It will soon be moving on to be textured.
Watch this one to the end, it includes all the variations of the M14 that will be in game.
<video autoplay loop muted>
  <source src="https://i.imgur.com/QaHOUtT.mp4" type="video/mp4">
</video>
<img src="https://cdn.discordapp.com/attachments/339047556430561282/626548597164605440/screenshot011.png" align=”middle” style="border:1px solid">
[Stefan’s Artstation Page](https://www.artstation.com/artwork/w8353V)




On the weapon animations front, **Haxorus** has finished the reload animations for the mp5 and variants:
<video autoplay loop muted>
  <source src="https://i.imgur.com/oj481Wq.mp4" type="video/mp4">
</video>




**Abiscuits** has been working on updating the old character creation menu to implement for internal testing and to allow for easy testing of Dogtooth’s hair and clothing. We’re not quite ready to show off the character creation screens or hair yet, though.
He has also been improving the Steam build process to increase the frequency of multiplayer tests. In the coming weeks he will be implementing more vehicle types to test as well as improving the in-game VoIP/radios.




**Dogtooth** has gotten some clothes rigged to the character and zombie models to give players more variety. He has also finished getting new hair and facial hair varieties created and set up on the character models.




**Regicidalnut** (RegiBless, AKA Me) has been working on fleshing out the timeline of events in Dead Matter, quest design, and the smaller “snapshot” stories that players will come across in various points of interest on the map. Don’t worry, quests won’t be called quests in-game. That’s far too fantasy-sounding. Players will be performing tasks, doing investigations, and completing assignments for the different factions on the map (if they choose to do so). For those that are eager to learn what happened in Alberta in the weeks leading up to and during the outbreak, exploration will be key. It’s really weird writing about myself in the third person.




**Shirk** has been working on fixing up the grass and general foliage for the game. He has also been working on fog elements to go with the new skybox and fixing up the map after some new updates.
 <img src="https://i.imgur.com/tD51rtJ.png" align=”middle” align=”middle” style="border:1px solid">
[High resolution version](https://cdn.discordapp.com/attachments/349385365892628480/624345804018024459/HighresScreenshot00095.png)
<img src="https://i.imgur.com/VQXGSB1.png" align=”middle” align=”middle” style="border:1px solid">
[High Resolution Version](https://cdn.discordapp.com/attachments/349385365892628480/624345809244258367/HighresScreenshot00096.png)
  <img src="https://i.imgur.com/UpOryFd.png" align=”middle” align=”middle” style="border:1px solid">
 [High Resolution Version](https://cdn.discordapp.com/attachments/349385365892628480/624345819297873928/HighresScreenshot00097.png)
 <img src="https://i.imgur.com/BGJRm4Y.png" align=”middle” style="border:1px solid">
[High Resolution Version](https://cdn.discordapp.com/attachments/454408995801661440/621830580539228201/HighresScreenshot00082.png)




Last week, Shirk spent most of the time fixing up miscellaneous assets in the world after finishing the rework of the skybox. Since the old skybox had inaccurate lighting, and the game uses DFAO (Distance Field Ambient Occlusion), many materials had to be darkened manually in engine to make sure they didn’t appear too bright and breaking lighting aspects like exposure and shadows. Materials like asphalt and foliage required the most adjustment.



<img src="https://i.imgur.com/DfHg5rR.png" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/IM3vcST.png" align=”middle” style="border:1px solid">
The leaves on the tree above are white because they get their color information through a texture lookup in UE4 that changes dynamically to match the seasons in-game.
<img src="https://i.imgur.com/LjJpv7g.png" align=”middle” style="border:1px solid">



Shirk has also been working on finalizing the collision for the buildings. The complex collision that was used for testing has reached a point that it was negatively affecting performance during tests. Every building essentially has to be reconstructed with simple convex shapes such as boxes and cylinders for collision. This change greatly improves performance when compared to the per-poly collision that was being used in testing.




The collision process Shirk is working on is the final step in the building design process, and it takes quite a while to do. This is why we have used the complex collision for testing because it makes testing navigation with doors, windows, stairwells, etc much faster. The new convex collision hulls allow us to control exactly the size and shape of collisions. This keeps small objects and details from hampering player movement through buildings. It does have the drawback of not being a 1:1 match with the underlying mesh, but for the majority of cases it will not interfere with gameplay.




<img src="https://i.imgur.com/XiLRxpe.png" align=”middle” style="border:1px solid">
Along with the new collision meshes, Shirk has also been working on making manual LODs (Level of Detail) in 3ds Max to simplify the meshes at a distance to remove details the player wouldn’t be able to see. This process can heavily affect performance by dropping the complexity of meshes at a distance and reducing the vertex counts (which can be very expensive at long distances) without sacrificing visuals since they are far away from the player. This essential stage is possible to do within UE4 with built-in tools, however by working in 3ds Max, Shirk can control exactly what he wants to remove based on distance.



<img src="https://i.imgur.com/VLz8oia.jpg" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/bTMo9Hs.jpg" style="border:1px solid">




A great example of this process is the above pictured overhanging shingles. They contribute a hefty amount of vertices to the mesh, but can only be seen when you’re within ~10 meters of the model. So removing them shaves 62% of the vertex count off the model by culling them at a distance (in the top left of the images you can see the vertex count in the top image drop from 1484 to 572 in the bottom image).




<img src="https://i.imgur.com/NjxbtnR.jpg" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/kkHGY4V.jpg" align=”middle” style="border:1px solid">




LODs could still be further reduced in the above image by culling the support posts or even the chimney at long distances, but doing so is a game of balancing time spent reducing models, visual differences at a distance, and working on other meshes.Here is another example using the roof of one of the gas stations:




<img src="https://i.imgur.com/NUZloxZ.jpg" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/p5gYCFQ.jpg" align=”middle” style="border:1px solid">
Note the vertex count dropping from 11,167 to 953 for a *91% reduction*.
<img src="https://i.imgur.com/U9V6Jf8.jpg" align=”middle” style="border:1px solid">
<img src="https://i.imgur.com/lgFQ3Qk.jpg" align=”middle” style="border:1px solid">




 In the coming weeks, Shirk will be getting back to work on world development with a new workflow approach that will hopefully speed up the process quite a lot and utilize more resources on the team. But we’ll get more into that in the next blog post.
For our forums users, we apologize for the forums still being down. With the site rework, we want to be sure the community has a great forum platform to communicate with us on. Unfortunately, choosing the right platform and properly integrating it with the new website is taking longer than anticipated. For the sake of transparency we are also working on trying to get the old dev diaries that were posted on the old forums archived within the new one. Rest assured, we will make an announcement as soon as the forums are back up and running.


**Alright everyone**, that wraps it up for now. As with anything we do, we love to hear your feedback, support, and constructive criticism. Thank you to all of you and our backers for making this project possible. We wouldn’t be able to do this without you and your support!


If you’re not a backer already, and want to support the development of Dead Matter, you can back the project at the following links:


[IndieGogo](https://www.indiegogo.com/projects/dead-matter-pc-community#/)


Or


[https://qisoftware.ca/store](https://qisoftware.ca/store)


But even if you can’t, or aren’t comfortable with backing just yet, just spreading the word to your friends and talking about the game helps a ton.


Until next time,


Regi


P.S. Plan Accordingly

