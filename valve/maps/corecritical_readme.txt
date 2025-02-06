					===================
					** CORE CRITICAL **
					===================
					
				A HLDM map by Hezus (2024)
				
	For the THWL Half-Life 25th Anniversary Competition


Background story:
-----------------
Far away from the Lambda Complex, the Black Mesa Research Facility built a much more advanced facility to develop the experimental portal technology: the EPSILON COMPLEX.

In here, a much larger machine was created to harness power from crystals retrieved from Xen in earlier missions. With this power and the new technology, the researchers could teleport targets on a much larger scale.

However, danger awaits for those who push the boundaries of time and space. Operate too close to the edge of the knife and who knows where you and your team might be swept off to...

(yes, it really needed a background story)


Description:
------------
The map is rather large and will require around 8 to 16 players to ensure enough action and chaos. The map supports up to 32 players.

Starting the server, the map will trigger 5 minute delay sequence before the experiment can be started in the control room. A announcer voice will supply a countdown to keep players informed about this status.

After triggering the experiment, a short sequence (much like HL's) starts and the machine will teleport every player to a Xen island. Everyone loses their gear and a wacky arena fight using Hivehands and Snarks starts. 

The Xen portion takes about 3.5 minutes and will then teleport you back to the facility. To indicate this time, the 3 large crystals around the island will fire a beam at the large central crystal. Once all beams are lit, the big crystal will flare up and initiate the teleportation.

After this, the entire system loops around again.


Technical info:
---------------
The map is *extremely* close to engine limitations. I've used up 99% of the entity limit (max 1200). I've also nearly reached the maximum of worldleafs, so I couldn't add anymore brushes.

The map has been tested to run on a 2-player server but if you want to make sure it doesn't crash, add some more slots to the server. The more slots you add, the more entities the engine frees up.  

The teleport sequence relies on a large amount of trigger_teleport fields (402 brushes). I've cut up the playable space in roughly 256x256 blocks, that are combined into 32 groups. These groups then form one of the 32 possible teleport destinations. Because of the high amount of individual blocks, the chance that players end up in the same destination is very small, but still possible. I started off with even more fields and destinations but this took up way too many entity resources for the map to still load. 

Between teleporting, the player is transported to a flashy green room to create a teleport effect. A trigger_push then changes the direction the player is thrown into a teleporter to either Xen or Earth. With this system, I was also able to create a cool teleport effect for spawning players, so no-one just appears out of thin air. 

The teleport box also strips players of their gear and gives you a new weapon. The make sure everyone gets those weapons, the map has a custom _load.cfg file that make sure mp_weaponstay is set to 1. Server owners can disable this but there is a small chance players will then spawn without a weapon. 

The map uses a custom WAD (halflife-extra.wad) but it has been compiled to be included inside the BSP. As per competition rules, all custom textures are variants of existing Half-Life textures. The only exception is the dripping water texture, which was made from scratch. I started out with a looping particle system but this took up many entity resources, so I settled on this solution instead (which only takes up 1 entity). I hope this is forgiven.

I've added BLACK_HIDDEN fields to all transparent walkways and the entire Xen area to ensure the player has correct model lighting.

During the test sequence, the power generator room also becomes slightly hazardous. I thought this was a fun thing to add to make the match more dynamic.


Build info:
-----------
I made this map in about four weeks, starting on the 4th of December 2023. Most of the map was done in about 2 weeks, and another 2 weeks for all the tweaks and details. The map initially started with the idea of jumping between the facility and Xen at will through large portals. After that I settled on the idea of a machine taking everyone there at the same time. This will function as a big reset in the middle of the fight and evens the playing field again by giving everyone just one or two weapons. During playtest, it was great fun going at eachother with the Hivehands and Snarks. The close quarters also makes it feel like a final stage in a Battle Royal game. The secret Gluon functions like finding the Redeemer in Unreal Tournament. It's a large gun, but will only give you 20 ammo once. 

I didn't plan out the layout for the facility beforehand because of the time contraints. I knew I had to just get on with mapping and not get bogged down. I just had the idea for the test chamber and as soon as the first version of that room was done, I just started plotting rooms around it. I Bob Ross'd it so the entire thing is now just one happy accident.

I designed everything with some simple rules in mind: I wanted each room to have at least three entry points and at least one variation in height. This worked quite well and most of the design is still the same from the very first draft. The only exception being the quadrant where the generator and the computer rooms are. Initially, I had a larger area with big mainframes but I didn't like the way it looked and it relied too much on walkways to get around. I already used this trope in the main chamber and the room with the two vats.

One thing I enjoy in DM maps are semi-secret backdoor routes, so I made sure to add a bunch of those. In the later stages, I've added lots of small details to make the facility feel alive and lived in. They do not serve any purpose in a DM map but it felt good to add them nonetheless.


Known issues:
-------------
- Due to a HL25 bug, the fans do not play any sounds.
- The small freight elevator has no sound because of a HL25 bug, where the sound would keep repeating and turn into unbearable noise.
- The buttons on the vending machines do not move. This is because I grouped them all together into one button to save entities.
- Longjumps are not taken away by the player_weaponstrip. This is a bug or lack of feature in HL.  


Hints:
------
- In Xen, there's a Gluon on a far remote island that can only be reached with a jongjump. The longjump is found on the opposite side of the island. Is it worth the risk trying to get it? For you to decide!
- In the room with the 2 large vats, there's a Gauss hidden behind a pipe on top of the highest vat. You can get to it by moving the elevator to the heighest point and then jump. Or if you're a skilled jumper, you can just make it from the top floor. 
- The Crossbow can be found on top of a computer in the green computer room. To get there, you need to go up a level and crawl through the vent to drop down.
- You can activate the backdoor route by using one of the big computers in the control room. You can spot the grate behind it.


Tools used:
-----------
- J.A.C.K. Editor
- Wally
- Photoshop CS6
- BSPguy

Compile info:
--------------
v1.0.1 ADM101 64-bit (Jul 24 2022)
CSG -cliptype precise -wadinclude halflife_extra
BSP -maxnodesize 1024 -nohull2
VIS -full
RAD -extra -bounce 8 -smooth 180 -smooth2 120 -vismatrix sparse -texlightgap 2
