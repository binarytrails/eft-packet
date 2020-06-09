```
Ectoplasm in [C++] Packet-based 3D Radar / psuedo-ESP at 23rd March 2020, 09:40 PM

I've been working on my packet-based 3D radar for a week now. Originally I was going to keep the code private. After being contacted by several users following my posts in the Packet Interceptor page ordering me to delete my existing posts and stop posting further information because they wanted to keep it secret, despite using the information in the thread for the creation of their own $100/user/month paid cheats. This rubbed me the wrong way, so I'm releasing my code for everyone to use, for free. At least until they add packet encryption, which, after the recent posts hitting the top of Reddit about packet-based ESP, is an inevitability, probably in the next patch.

This release includes source code only. If you are not a developer, this post is not useful for you. I won't provide technical support for non-technical users trying to build and run this. Make sure to read through this thread before asking any questions. If your question is "how do I run this", it has certainly been answered.

https://github.com/ucectoplasm/eft-packet

https://i.imgur.com/GkGTGG5.png

Headline features:

- Packet-based radar, use a managed switch to mirror traffic from your PC to a second PC, then intercept the traffic on the second PC to get live data undetected.
- 3D rendering. This isn't a top-down 2D map that shows you loot and approximate positions. This renders from your perspective in a 3D world.
- Player, enemy, npcs position/orientation. Tell the difference between enemy players, enemy scavs, and npc scavs. Highlights group members in green.
- Displays when other players have extracted.
- Elevation matters; things above and below of you (most likely out of sight) are partially see-through.
- Shows loot. Loot filtering not included. Write it yourself! (if you want information about loot, you need to extract the loot database json file from the game assets. I'll leave this as an exercise for the reader.)
- State recording and replay. This is mostly used for development, but you can record all of your games and replay them back (inside the tool) for any reason you'd like. Read the code to figure out how.

Thanks to @koray37, the project now has a CMake build system set up. Building should be obvious.

Want to improve it? Here's a TODO list:

- Make loot despawn when somebody picks it up.
(hint: probably in the game world update packet)

- Make text face the camera.
(hint: billboarding, may be able to accomplish this without editing the text library with some view transformation shenanigans to gltDrawText3D)
(hint 2: if maths is scary, just draw the text in screen space instead, but be aware this will force text to render in front of everything else)

- Search the code for TODOs and go wild.

- Ultimate TODO for masochists: Read the Unity level format for the current map and render the game world inside the hack.

Credits:

Marik and escapefromlobby for the back-and-forth collaboration during the development process. Various users in the Packet Interceptor thread.
Last edited by Ectoplasm; 5th April 2020 at 04:26 PM.
```
