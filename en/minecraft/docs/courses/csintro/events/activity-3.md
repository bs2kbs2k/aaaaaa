# Activity: Last Stand at the Alamo

In this activity, you will recreate the experience of being overrun by hordes of zombies. You will also see the effect of exponential growth: every time you kill one zombie, many more will be created to take its place. What does that feel like? Let’s find out!

The event handler that you will be using is `||mobs:on monster killed||` to trigger new zombies to spawn when one is killed.

## Do the activity

### Respond to a mob killed event

1. From the `||mobs:Mobs||` Toolbox drawer, drag a `||mobs:on killed||` block into the coding Workspace.

```blocks
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), function () {

})
```

### See whether it was a monster

1. From the `||mobs:MOBS||` Toolbox drawer, drag a `||mobs:monster||` drop-down block out to replace the default, `animal`.

2. Using the drop-down menu in the `||mobs:monster||` block, select the `zombie` spawn egg.

![pick the zombie mob](/static/courses/csintro/events/pick-zombie.jpg)

### Get set up to spawn new zombies!

Now let's set up the game so that when a zombie is killed, two new ones will spawn at a random location near your player.

1. From the `||mobs:Mobs||` Toolbox drawer, drag a `||mobs:spawn animal||` block under the `||mobs:on killed||` event handler block.

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
})
```

### Select the zombie egg

1. Similar to what you did in step 2, here you need to replace the default `animal` setting with `zombie` in the `||mobs:spawn||` block.

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.create(0, 0, 0))
})
```

### Two zombies are better than one

1. You want to spawn two zombies for every one you kill, so from the `||loops:Loops||` Toolbox drawer, drag a `||loops:repeat||` loop onto the work area. This `||loops:repeat||` loop should be inside the `||mobs:on killed||` event, and your `||mobs:spawn||` block should be inside the `||loops:repeat||` loop.

2. In the `||loops:repeat||` loop, enter the number **2**.

```blocks
 mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.create(0, 0, 0))
    }
})
```

### Where to spawn the zombies?

Now you need to tell Minecraft where to spawn the zombies. Notice that, by default, the relative coordinates are set to your player’s current location `(~0 ~0 ~0)`. Relative coordinates are covered in more detail in Lesson 3. If you use `(~0 ~0 ~0)`, you will spawn two zombies right on top of your character. This isn’t a great idea, so let’s make the new zombies show up just a little farther away, at random locations.

1. Replace the default `(~0 ~0 ~0)` with a `||positions:pick random position||` block.

### ~ hint

The Toolbox search is your friend! Use it to look up blocks or events you are not sure about.

![pick random position](/static/courses/csintro/events/pick-random-position.png)

### ~

### Set the random position range

The two sets of coordinates in the `||positions:pick random position||` block describe opposite corners of a box within which zombies will spawn at random locations. Let’s choose a box 10 blocks around your player, which should create an area of 441 square blocks centered on your location.

1. In the `||positions:pick random position||` block, enter the `from` coordinates as **(~10 ~0 ~10)** and the `to` coordinates as **(~-10 ~0 ~-10)**.

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.random(
            positions.create(10, 0, 10),
            positions.create(-10, 0, -10)
        ))
    }
})
```

### ~ hint

In Minecraft, 0 counts as a place to put blocks, so 10 to -10 is actually 21 places. 21 x 21 = 441. That is where the number 441 comes from. This might make more sense after you complete [Lesson 3: Coordinates](/courses/csintro/coordinates).

### ~

**Shared Program:** https://makecode.com/_VseXqc2Vjbv9

### Try it out!

When you are playing with zombies, everything has to be just right. Zombies are kind of grumpy at times.

Open a Minecraft world suitable for meeting a zombie in. Before testing your code, it is important that you get a few settings correct. You can do this by using terminal commands after you are in a world.

## ~ hint

**The Terminal and the Chat Window**

The chat window and the terminal are the same thing in Minecraft. Minecraft has one window in which you can enter chat messages, just like in any messaging system, and where you can also enter commands as you would on a computer terminal. Terminal commands are typed-out words that tell the computer what to do. For instance, instead of using the mouse to double-click and open a program, you could type the name of the program and press `Enter` to open it.

## ~

You will set the gamemode to Creative and the difficulty to Easy, and you will use your fists for this first experiment.

1. While in a world, open the terminal (chat window) by pressing the `T` key.

2. Set the gamemode to Creative by entering the following command in the chat window and pressing `Enter`:

> ``` /gamemode c

    <br />3. Set the difficulty to Easy by opening the chat window again and entering the following command:
    
    &gt;```
    /difficulty easy
    

Next you need to equip the spawn zombie egg. Press `E` to open your inventory. You can search for this!

![spawn zombie inventory](/static/courses/csintro/events/spawn-zombie-game.jpg)

Throw out an egg and create a zombie. In Creative mode, the zombie will not attack you, but zombies like rough play, so go ahead and chase your zombie. Hit the zombie until it dies. You should see new zombies spawning after each zombie is killed. That is your code working!!! Test it out further...

## ~ hint

**Clear All Zombies**

If at any time you want to "reset" the situation, you can kill all the zombies and start clean by using this command in the terminal:

    /kill @e
    

This kills all entities.

## ~

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Create Cave Spiders

Use the existing `||mobs:on killed||` event, but change a few things. How would you spawn five cave spiders every time a cave spider is killed?

### Challenge 2 - Make a Friendly Zombie Act More Like a Real Zombie

Now you'll change the monster back to zombie and set your code to spawn five zombies every time a zombie is killed.

Ok, all this is good, but it's not exactly like the zombie or monster movies. These entities (zombies and cave spiders) are acting too friendly and do not do anything when you hit them. This is because you are in Creative mode. You can use the `||loops:on start||` event to trigger a more zombie-like mood!

To do this, you need to add the `||loops:on start||` event and change the mode to Survival. Can you find these blocks in the Toolbox drawer and set this up?

The code should change the mode to Survival on start. Then, if there are any zombies, you will notice that they will chase you.

### Challenge 3 - Get Ready for the Horde

You want your assault on the zombie horde to begin the same way each time. It would be nice to be able to start the zombies whenever you want without having to equip spawn zombie eggs. Also, too many older zombies from your previous plays might still be hanging around, so you need to eliminate them to clear the world. You want to have a fresh start if your player dies. Finally, what about giving your character something to protect themselves with?

To do these things, let's use a new event, `||player:on died||`, and add a `||player:on chat||` event as well.

First, clear out all the old zombies in the `||player:on died||` event.

1. Kill all old zombies after you die... revenge! (Kill all entities.)

Can you add a block to the `||player:on killed||` event to make this happen?

Next, let's spawn one zombie when you enter the command **Z** in a `||player:on chat||` event. You also want to give yourself an iron sword at this time so your character can protect themselves.

1. Add a `||player:on chat||` event.

2. Spawn one zombie.

### ~ hint

Use these coordinates:

![spawn zombie coordinates](/static/courses/csintro/events/create-zombies-coordinates.png)

### ~

1. Give yourself an iron sword.

### ~ hint

The Toolbox search is your friend! Use it to look up blocks or events you are not sure about.

![walk through air](/static/courses/csintro/events/toolbox-search.png)

### ~

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - A Ranged Weapon for Your Player

What if your player inventory already had a weapon - ideally a ranged weapon like a bow - at the beginning of the game? You will need some arrows as well. Try other weapons or items! Arm yourself with blocks and try to build a wall to stop the zombies.

### Experiment 2 - The Perfect Zombie Movie

Now that you have played around with some events, you might add even more to them to create the perfect zombie movie setting. You could change things like the time of day or the weather, spawn more monsters, or do other things to start the game with a real rush. Maybe you could equip your player with a weapon like a bow and arrow so they have a better chance at surviving! Give some of these ideas a try to set up your zombie apocalypse!

![zombie movie setup](/static/courses/csintro/events/zombie-movie.jpg)