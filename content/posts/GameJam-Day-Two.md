+++
date = '2025-11-05T23:41:37Z'
draft = false
title = 'GameJam Day Two'
+++

# Game Jam Day Two: The Adventure Continues

I got into the lab for 9:50am only to be told that one of my team members wouldn’t be in until 12 or potentially after and the other team member hadn’t contacted me so I began work immediately.
Todays first task? 
Scrap 	yesterdays object interaction system…

That’s right! Scraping all the work I did yesterday or more accurately, I was going to innovate on the simple system I had implemented yesterday and change it to allow the player to hold objects in their hands without the need to press and hold down a specific button, this would make carrying small items around the game world 10x easier especially when concerning the puzzle elements.
So I got to work back tracking my idea.
The task itself involved creating a blueprint for every small interactable object within the game world, something that can be used multiple times by simply changing the mesh of the object to represent a different interactable object like toys, cutlery or a pillow for example.

Just like last time, I would be focusing on the player character blueprint first.
I spent a good half an hour looking at tutorials before realising that without a first person perspective the act of holding an object in your hands as the player character wouldn’t look so good. So I decided to focus on updating the previous days script to add the ability to throw the object when a button was pressed instead.
The first thing I had to do was create a new input action for the act of throwing an object. These inputs allow actions to be done as the player when certain conditions are met such as pushing a button to jump.
So following the naming conventions of the other input actions I created a new one and named it IA_Throw.

![](images/throw.png)

I mapped it to F on the keyboard and set it up so that whenever the F key is pressed the object in hand is thrown.
Next I went to work on the actual code that would allow for the checking of the input and execution of the required behaviour. And so my work on the player character blueprint began again.

Now usually I would need to implement code that would allow any grabbed object to attach to a created socket on the character (like connecting two Lego pieces). However, as this was day two of three of a GameJam such things could be simply ignored for the sake of saving time. This would make my work easier and allow me to get straight to coding the behaviour itself.

![](images/grabthrow.png)

After following a tutorial I managed to construct rudimentary code that in theory would allow me to throw an object held by the player. I say “in theory” because…It didn’t work.

It turns out I would need to go back to the drawing board however, I still had my original code from yesterday so for the time being I decided to use that and put my focus on the push and pull interaction system which was vital to the completion of all the puzzles.
After a couple hours of messing around with options to replace my simple code, I went to have lunch slightly dejected.

When I returned 20 minutes later, my other team members had arrived and we begun to set up Perforce which was necessary if we wanted to work on things away from the lab. However, after multiple attempts that turned out to be unsuccessful, we decided to ditch Perforce and switch to GitHub to host our remote repository. This proved easier to set up and maintain as I had already used GitHub for such things so all that was left was to spend some time uploading our project files and sharing access to all team members.

The process of getting everyone on the same page however had some issues, pulling the origin became a problem as we all had uncommitted files for our local game files so we each had to fix the problem by committing our modified game logs and somehow that fixed the problem and we were able to begin work again.

We began by uploading 800+ Texture and mesh files for objects ready to replace the base model mesh files for all the objects blocked out in day one by the level designer.
While one team member was doing that, the level designer was finishing the block out on room one and two.

![](images/blockout1.png)
Room 1 blockout.

![](images/blockout2.png)
Room 2 blockout.

Once both block outs were done, the level designer began gathering all relevant links related to assets for a credits document as specified at the start of the Game Jam this would allow the person marking the entries to see where we acquired the assets we used to populate our game world.

At that point, I had decided I would attempt any code additions I didn’t do today at home so I could better understand the tutorials as the computers in the lab we were working in did not have speakers making tutorial work more difficult and time consuming. This would allow me to complete any outstanding behaviour work I had left to do for the day primarily the throwing mechanic and the push and pull functions for moving bigger objects like chairs and boxes around the game world as well as make any additional changes necessary to existing blueprints and files.

With the clock officially hitting 6:30pm, we decided that we would push the last progress for the day to the GitHub repo and head home.
However, as there was still a lot to be done I knew I had to do some work away from the lab. So after I returned home I set myself the task of implementing the push and pull mechanic I attempted earlier in the day unsuccessfully. I would once again be using a tutorial however, unlike last time, this time I would actually be able to listen to what was being taught to me.

Unlike my earlier tasks implementing the simple grab and throw mechanics, this task was a lot more complex involving advanced collision mechanics and multiple forms of input involving the player character.

I began by cloning the repository for the project onto my home computer and immediately got to work on the required code.
I created the blueprint that would be used for all large moveable objects present in each level such as chairs or boxes. I then accessed the testing level that was setup specifically to test new content in order to prevent anything from going wrong in the main three levels

![](images/testroom.png)

I then added a box collision which would allow the player to interact and also allow me to check if the player can interact with the chosen large object.

![](images/largeobjectbox.png)

Next, I moved onto the behaviour code.
I implemented code that would print a string that shows a character can push something when overlapping the box collision and will also show up when the player and the box collision are not overlapping to show the player can't interact.

![](images/testingroomobject.png)

Next, I moved onto creating the boolean interacting check variables for the player character blueprint, isInteractingBox and CanInteract.

![](images/booleans.png)

Once I had those done, I created a simple check system with those Booleans to check if the player is interacting with the object and if they are then setting the max walk speed to around 60 to be slower. However, if the player is not interacting with the object or stops interacting with the object then the walk speed gets reset back to maximum.

![](images/codecheck.png)

The next part simulates physics if the player is interacting with the object.

![](images/physicscode.png)

After that, I moved onto the interaction within the large object blueprint using event tick. This also involved changing the player input code which I found quite complicated but completed it regardless.
However, after 2 hours of work the resulting code didn’t function and after looking into the issue, I came across the problem, the input actions used in the tutorial are officially depreciated in the version of Unreal Engine 5 I was forced to use for this GameJam making two hours of work irrelevant.

At that point the clock had officially hit 3:20am on the 6th of November (My birthday) and I decided it was time to sleep.
Only one day left and I am determined to finish the necessary code before the deadline.
