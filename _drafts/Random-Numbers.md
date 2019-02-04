---
layout: post
title: Random Numbers
---

I believe that to really begin a discussion about procedural content generation (hereafter referred to as PCG), one has to start with random numbers. They are the foundation of what makes up most other PCG strategies, yet they are often overlooked when giving advice on where to start with when learning about PCG. In this post I'm not going to teach you how to make a call to a random number method. I assume you already know that. Instead I want to get you thinking about how powerful just calling that method is. So go ahead and close down your code editor and get yourself a pen, sheet of paper and a 20 sided die.

If you don't have a d20 you can use the d20 simulator I have included right in this blog post. Keep clicking the button to get a new result.
{% raw %}
<button id="d20" onclick="rollDice()">roll</button>
<script>
function rollDice() {
  document.getElementById("d20").innerHTML = Math.floor(Math.random() * 20) + 1;
}
</script>
{% endraw %}

## The Original PCG
I am a huge fan of the game Dungeons and Dragons and other similar tabletop role playing games. I have two groups and often play two games a week. There are a lot of ways to enjoy D&D but my favorite is by making everything up as we play. In one of my games I'm a player, my character is a half-elf rogue who specializes in disguise and subterfuge. For my other group I am the dungeon master, which means I am responsible for making up everything that the players experience in the game. Yet I have a full time job, far too many hobbies, this blog being one of them, and a 6 year old son. I don't have time to make up a bunch of stuff ahead of time! So how do I do it? My games are procedurally generated.

## Random Tables
I own hundreds of dollars worth of D&D books. Much of the content within those books are random tables. Random tables are simply numbered lists of things. They can be location descriptions, character descriptions, enemies, or anything else you might want in your game that you are willing to let your dice decide on for you. Sometimes these tables can contain much more than 20 items and many of these tables are actually lists of other tables! In our example we'll keep it simple though.

## Your First Procedurally Generated Encounter
Lets say your players are walking through a trail in the woods, what is the weather like? We can use a random table to determine this. Use your d20 and the table below to decide.

| Roll | Weather |
| ----- | ------ |
| 1-5 | Dark and stormy |
| 6-10 | Bright and sunny |
| 11 - 15 | Cold and gloomy |
| 16 - 20 | Warm but overcast |

Now your players enter a clearing. In that clearing they find

| Roll | Found |
|------|-------|
| 1 -2 | A pile of treasure |
| 3 - 4 | A goblin encampment |
| 5 - 6 | A strange hut |
| 7 - 8 | A swarm of biting flies |
| 9 - 10 | A wizards tower |
| 11 - 12 | A unicorn |
| 13 - 14 | A cave |
| 15 - 16 | A bandit encampment |
| 17 - 18 | An enourmous pile of dung |
| 19 - 20 | An ork encampment |

By now you should already see how powerful a random number between 1 and 20 is for creating unpredictable game content.