---
Title: (Canadian) Thanksgiving Development Update
Description: In this post we show off some new Backer weapons, some of the WIP perks systems that players will use, and dig into blockouts and the struggle for good reference images with Shirk. We’re happy to keep these blog posts coming in our continuing effort to increase transparency and communication with the community.
Author: Regicidalnut (RegiBless)
Date: 10/11/19
Template: post
---
# Canadian Thanksgiving Development Update
Happy (Canadian) Thanksgiving weekend! The forums are now officially up and running! Feel free to create your account and join or start a discussion. We’re working on getting Backer badges functional on the forums as well as getting the old Dev Diaries and news threads archived for transparency and those interested in reading back.
As a quick reminder, **anything shown on this blog and on the vlogs, is a work in progress** and is subject to change as development continues.
### Dev Updates:
Anyone not mentioned has been working on things we’re not quite ready to talk about to show off at the time this blog was posted.




**Nomad** is currently working on gameplay elements for the mine that was highlighted in [Vlog 09](https://youtu.be/ue_vkZA3GFQ) as well as helping Shirk with building blockouts for the map. He wants the mines to be an interesting yet dangerous place point of interest that contains useful survival items that will be found in refuge chambers dotting the site.
<img src="https://cdn.discordapp.com/attachments/626542398759108618/631991757755777024/HighresScreenshot00269.png" align=”middle”>
Players will have to contend with hazards like toxic water flooded chambers and noxious gas that will require some exploration and problem solving to pass. Nomad and Nik discussed a few different options for making some rooms within the mine interactive, and Nomad went ahead and made a simple prototype with Unreal’s built-in media framework that allows for files to be played on a material.
<video autoplay loop muted>
 <source src="https://i.imgur.com/Qq59Eo2.mp4" type="video/mp4" style="border:1px solid">
</video>
Note: The UI shown is not final and is a test of the aforementioned system.
Using this method, Nomad can plug the other bitmaps used for the display and keep the monitor from looking out of place when switching on and off. The downside to this method is that a video file will have to be created for every option presented to the player, which could balloon the storage space required by the game. Another option being explored is the UMG UI tool that comes with Unreal. The look and feel of the software used in the mines will look very old - Windows 95-98 old to be precise.
Lastly, Nomad has been working with Shirk on the blockout of miscellaneous shops and buildings that will dot the streets of Canmore to give a better idea of how the final town will look.




**Tac_Error** has been working on the M-416 with barrel variants of 11”, 14”, 16”, and 20” versions. From here, he’ll be moving on to working on making more attachments for the ARs and 416s. Along with those attachments, the legendary variant of the 416 will be finished.
<img src="https://i.imgur.com/5f1Dt9h.png" align=”middle”>
<img src="https://i.imgur.com/QWB7NGn.png" align=”middle”>
<img src="https://i.imgur.com/CtQRfYi.png" align=”middle”>
<img src="https://i.imgur.com/gFHQ3KZ.png" align=”middle”>
**Gunschlinger** has been working on some of the door programming. There will be doors that need to be interacted with to open, doors that operate on physics both way, and swing doors that can be pushed open from one direct and require interaction from the other. The new doors will also interact with AI and Infected, so if players flee through a door, it’s possible the Infected can push through in their chase.
<video autoplay loop muted>
 <source src="https://i.imgur.com/wyXMvf8.mp4" type="video/mp4" style="border:1px solid">
</video>
He has also been working on the occupation and perk point system that will dictate what player characters are proficient in as well as their spawn gear and stats. **This is another reminder that things shown here in the blog, including these perks, their effects, and possibly their inclusion in the game, are subject to change and still a work in progress.**




Players will be given a pool of points to spend on perks for their characters before they spawn. Choosing these perks will not affect starting gear, only what aspects of the game they are proficient in. The strongest groups will be able to coordinate these perks with one another’s strengths and weaknesses for a well-rounded group of survivors. Any chosen occupation will come with “preinstalled” perks that players will get for free, and each occupation has a set amount of points to be spent on additional perks.


Here are some positive perks that have been implemented:
- Desensitized - Immune to suppressive fire
- Slow Metabolism - Character needs to eat less
- Low Thirst - Character needs to drink less
- Athletic - Faster vaulting and running speed
- Thief - Faster crouch speed
- Low Profile - AI has a harder time detecting you
- Thick Skin - Less likely to bleed when injured
- Partyboy/girl - Less likely to get drunk
- EMT - Character uses medical items faster
- Country Born - Identify poisonous plants easily
- Pistol Proficiency - Better with Pistols
- Rifle Proficiency - Better with Rifles
- Shotgun Proficiency - Better with Shotguns
- Melee Proficiency - Better with Melee
- Handyman - Faster Crafting speed
- Scrapper - Crafting requires less resources
- 5 Star Cook - Character can cook advanced food - 
- Engineer - Character can craft advanced items
- Swimmer - Faster swim speed
- Mechanic - Character repairs vehicles faster
- Driver - Character is better at driving/handling vehicles
- Donor - Forces your BloodType to be O negative




And for balance, players will have negative “perks” they can take to increase the amount of points they have to spend:
- Paranoid - Play random gunshots around the character
- Clumsy - Make sounds while crouch-walking
- Fast Metabolism - Character needs to eat more
- High Thirst - Character needs to drink more
- Osteoporosis - Higher chance to break your bones, lower limb health
- Obese - Slower walking, running, and vaulting speed
- Peanut Allergy - Cant consume products that contain peanuts
- Diabetes - Requires Insulin every now and then
- Lactose Intolerant - Can’t consume milk products without negative effects




**Again, this is a reminder that things shown here in the blog, including these perks, their effects, and possibly their inclusion in the game, are subject to change and still a work in progress.**




Perks will be shown on the Character Stat screen and reflect the impact they have on player characters. Occupations chosen will also affect character SEDA stats. We are trying to include perks that are more interesting than simple “Player does X task Y% faster”. ```




<img src="https://media.discordapp.net/attachments/567094929088708630/632229091407298561/unknown.png?width=721&height=391" align=”middle”>




**Rizzler** has been working on putting some props and player containers such as luggage together.




**Stefan** has finished modelling and texturing base weapon as well as the Backer skin for the Dragunov shown in the last blog post. The engraving and little details are really going to set this weapon apart when the Backer that chose it is running around Alberta with it.
<img src="https://cdn.discordapp.com/attachments/454408995801661440/629077003039145994/screenshot000.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/454408995801661440/629077001952559106/screenshot001.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/454408995801661440/629076999851212830/screenshot002.jpg" align=”middle”>




**Shiny Haxorous** has been working on replacing the sounds for many of the pistols and rifles, cleaning up animations, and prototyping the ability to wield a flashlight and pistol at the same time. He has also implemented new C7/8 textures created by one of our contributors, Alex Scorpion (Here’s a link to [His Artstation Page](https://www.artstation.com/alexscorpion)), as well as the integrated receiver for the C8.




<video autoplay loop muted>
 <source src="https://i.imgur.com/ZuoxlDZ.mp4" type="video/mp4" style="border:1px solid">
</video>




<img src="https://i.imgur.com/S5dxXZW.jpg" align=”middle”>
<img src="https://i.imgur.com/Tmglie8.jpg" align=”middle”>
<img src="https://i.imgur.com/Rq2bJzQ.jpg" align=”middle”>
<img src="https://i.imgur.com/KEJhqvB.jpg" align=”middle”>
<img src="https://i.imgur.com/o05ZSuo.jpg" align=”middle”>




**Shirk** is continuing his work on the collision meshes discussed in the [September blog post](https://playdeadmatter.com/news/posts/developement-blog-02)
Since the last blog, Shirk has been working on the collision and LODs (Level Of Detail) for buildings.
<img src="https://i.imgur.com/X7dTSEy.png" align=”middle”>
<img src="https://i.imgur.com/yfZMh34.png" align=”middle”>




 There is still more to be done, of course, but to break up the monotony of the work he has also been working on the blockout phase of a bunch of buildings for Canmore. After he took a break from world development to work on the new sky and foliage, Shirk decided that he wanted to re-examine the workflow he had been using up to that point. As the Lead Artist, he decided that the previous workflow wasn’t working fast enough for the needs of the game. In the old workflow, he would start with a simple blockout of a building, and bring it to roughly 80% completion - lacking things like interior detailing, metagame connections, doors, useable items, and collision. The process could take anywhere from a day to a week for a single building, and while the process worked when the end goal of the building was clear, it didn’t work well if the art needed to be reworked for gameplay or layout design.




With the old buildings, if we found that a building was missing something from the layout or the scaling was a little off, it could be difficult to fix once the art had been completed. For example, if we decide that a building needs to have common facilities like a bathroom, kitchen, or furnace, but the building has already been designed and built without those things, it would be difficult or next to impossible to fix without totally scrapping the building or an aspect of gameplay with the building.




The purpose of the blockouts is to allow us to make sure the building fits all the gameplay needs from the start, then build the art around that. Blockouts are little more than very basic geometry that supports gameplay. So things like floors, walls, stairs, doorways, and anything else that focuses on gameplay are the main focus. This change to the workflow allows us to focus on the gameplay first and develop the map faster. It also allows for playtesting with a variety of locations rather than spending an equal amount of time on a much smaller location that has more detail. In the end, it means more content to explore at the cost of having fully detailed environments, but less variety in them.




The first building getting the blockout treatment has been the Canmore Safewee. If you’ve seen this building in real life (or on Google Maps) you’ll recognize the architecture similarities.




<img src="https://i.imgur.com/5QqkHuU.png" align=”middle”>




Though the blockout is fairly simple, Shirk is focusing on making sure the silhouette is recognizable at a distance so the building isn’t basically a giant rectangle.
<img src="https://i.imgur.com/pgzxKDC.jpg" align=”middle”>
<img src="https://cdn.discordapp.com/attachments/369755713351974912/631964354056552538/unknown.png" align=”middle”>
<img src="https://i.imgur.com/EUOrz8v.jpg" align=”middle”>




The goal in these building designs is to capture landmarks in certain areas as well as the overall aesthetic of the location. Canmore, being a mountain town, has a different architecture style than elsewhere in the Calgary area, and that’s something we want to capture. This attention to detail requires a lot of custom content and many hours spent scouring Google Maps trying to find as many reference images as possible. Since Shirk has never been to Canmore, let alone Alberta, it can be difficult to find accurate references. Even when he does, piecing them together is a chore in itself.




The Safe*way* Canmore’s Safe*wee* is based on is a great example. Shirk can dive into Google Maps, find the address, and get a decent look at the exterior of the building from three of four angles. This means he has to try and find a reference image of the back of the building, which takes some digging due to its location (there is a field, train tracks, and then another set of buildings blocking the view of the rear of the building on Google Maps). Fortunately, by pure luck, someone on the internet decided they wanted to take a picture of the rear of the building, but not the whole thing.
<img src="https://i.imgur.com/wXsGGqq.png" align=”middle”>




By using a nifty program called PureRef that lets him copy and past any images he finds into one place, whenever he finds a great reference image like this he can save it forever as a reference.




<img src="https://i.imgur.com/2zs7pMX.jpg" align=”middle”>




The interior design of these buildings is different nightmare altogether. Finding proper, usable reference images of the interiors of buildings is incredibly difficult, moreso when the building is a private location or large and complex. Most of the time, if he’s lucky enough to find a reference image, he will have to guess roughly 90% of the layout and design and go from there. Something that helps a ton is when he’s able to find a blueprint, layout, or evacuation plan map similar to what he’s designing. Since he’s never worked in a grocery store, he has no idea what the general layout would be for employee-only areas like back rooms, storage, offices, and so on.
<img src="https://i.imgur.com/zPw7UnK.png" align=”middle”>




When he finds an image like the layout above, it provides him with all the essential and auxiliary rooms that a typical grocery store would have, and their relative locations in the store.




There is a ton of work that goes into these buildings, and Shirk said he is always learning new things in his research into how they are constructed and organized. He added, “I’m frequently disappointed when I play games and the design of the buildings just don’t make sense. So I hope in the end that people will appreciate all the work spent attempting to make these buildings as accurate as I can to real life.”




**Alright everyone** that wraps up this development update. Thank you all for your continued support, and we look forward to hearing your feedback.


Plan accordingly, 


Regi

