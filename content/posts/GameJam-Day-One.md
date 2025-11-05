+++
date = '2025-11-04T18:32:41Z'
draft = false
title = 'GameJam Day One'
+++

# GameJam day one: It begins!

The jam started at 12pm and after the brief discussion of limitations and expectations as well as finding out that the use of Perforce was not currently available to share files actively amongst team members we had three days to build a game around a theme. The first hour was obviously spent coming up with ideas and deciding aesthetic. The theme was...

# **Escape Room**

So i teamed up with two of my classmates and we got to work on deciding how we would approach the challenge of creating a game around the theme provided. After much deliberating and back and forth on whether our project should be presented in a first person or third person perspective, we decided that third person would fit best and so we began to build the idea that would become our GameJam project.
After sometime we came up with the idea of focusing on a child character trapped in the house of a witch and shrunken to miniture size he must navigate three rooms of the house overcoming the obsticles presented by his size and solving puzzles with the aim of safely escaping the witch.

With this idea in mind we offically began the development phase.

while we were unable to share files at that current moment we decided to do our respective roles in seperate projects and simply upload the files to Perforce when the option became available which we were told would hopefully be on day two of the jam so with that in mind we got to work.

To begin we created the project using a third person template which comes with a precreated character blueprint allowing for the quick integration of character based features.

![](/images/gamejamtemplate.png)

Using this, i was quickly able to create code within the prexisting player character blueprint to create the ability for the player to grab objects with the left mouse button.

![](/images/gamejamgrab.png)

What this code does is first check whether the left mouse button is being pressed then checks the world location and rotation and whenever a object is grabbed the code then gets the physics component at the world location and sets "isgrabbing" to true.

If the left mouse button is released then isgrabbing is set to false and the physics component is released allowing the object to fall to the ground.

![](/images/gamejamgrabupdate.png)

I followed that up with code that checks if the object is picked up and if it is it gets the world location and rotation again and does some maths which allows it to set the new location of the object.
The result was this.

![](/images/gamejamgrabfinal.png)

While i was working on all of that, the other members of my team were hard at work on level design and asset aquisition respectively. 

The level designer came up with the idea of first blocking out a level with simple shapes while we waited for the last member to aquire the assets necessary to give out project a unique look.
Since we had the idea about a witches house we all agreed the look of the textures should be cartoonish and colourful in nature so the third member of our team set out to find free assets that share similarities in both colour usage and distinct look.

By this point however, the clock had hit 5:30pm and with the building closing soon we all made the collective decision to head home for the day.

That concluded the first of the three days of the GameJam.
The next day would present its own challenges and progress.