# Activity: Leap of Faith Mini-Game

Students love to create mini-games in Minecraft for their friends to play. In this activity, you’re going to create a simple mini-game that creates a tiny pool of water, then transports the player to a little platform 64 blocks high where the only way down is to jump and land in the pool of water! If you jump and miss the pool of water, you lose. Luckily, you’ll build this mini-game in MakeCode by using functions, so you can try again and again.

Your mini-game will have three parts:

1. Creating the pool of water

2. Creating the platform

3. Teleporting the player to the top of the platform

## Do the activity

### Make a function

1. Create a new MakeCode project called **Leap**.

2. Click the Advanced tab on the Toolbox to display more Toolbox categories.

3. In the `||functions:FUNCTIONS||` Toolbox drawer, click the **Make a Function** button.

![Make a Function](/static/courses/csintro/functions/make-a-function.jpg)

### Name the function

4. Name this function `pool`, and click **Ok**.

![Name the pool function](/static/courses/csintro/functions/name-function-pool.jpg)

### Make the *platform()* and *teleport()* functions

5. Repeat the previous step to create two more functions named: `platform` and `teleport`.

6. From `||player:PLAYER||`, drag `||player:on chat command||` onto the Workspace.

7. Rename this `||player:on chat command||` to `"play"`.

8. From `||functions:FUNCTIONS||`, drag the three blocks `||functions:call function pool||`, `||functions:call function platform||`, `||functions:call function teleport||` into `||loops:on start||`.

```blocks
pool()
platform()
teleport()
function pool(){}
function platform(){}
function teleport(){}
```

### ~ hint

The `||loops:on start||` block runs when the program starts. This can be a pain at times if you are testing code or want to restart the program. Use the buttons in the lower-left corner to restart your code on these occasions.

1. Click the stop button in the lower-left corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

2. Restart the coding environment. Click the play button. If the play button is not on, then your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

### ~

This will be our main program to start our mini-game. Hopefully, you can see how functions help to organize our planning when coding. Now, let’s build out these three functions.

### Fill in the pool

The first thing you’ll do is create a pool of water.

9. From `||blocks:BLOCKS||`, drag `||blocks:fill with||` into `||functions:pool||`. `||blocks:fill with||` will fill a three-dimensional box from the first set of coordinates to the second set of coordinates.

10. Using the drop-down menu in `||blocks:fill with||`, select a block of water.

11. In `||blocks:fill with||`, enter the following values for the first set of from coordinates: `(0, -1, 0)`.

12. In `||blocks:fill with||`, enter `(2, -3, 2)` as the second set of coordinates.

```blocks
function pool() {
    blocks.fill(
    blocks.block(Block.Water),
    positions.create(0, -1, 0),
    positions.create(2, -3, 2),
    FillOperation.Replace
    )
}
pool()
```

This will make a 3 x 3 x 3 pool of water that is located below our player’s feet.

After the pool is built, a platform will need to be built high in the sky. There’s no need for a tower or a ladder - there’s only one way down! You want to create a wooden platform that is slightly offset from the pool below so that you have at least a chance of jumping off the right side of the platform and landing in the pool.

### Build a platform

13. From `||blocks:BLOCKS||`, drag another `||blocks:fill with||` block into `||functions:platform||`.

14. Using the drop-down menu in the `||blocks:fill with||`, select a `DoubleWoodenSlab`.

15. In the `||blocks:fill with||` block, enter the following values for the first set of from coordinates: `(1, 64, 1)`.

16. Enter the following values for the second set of to coordinates: `(3, 64, 3)`.

```blocks
function platform() {
    blocks.fill(
    blocks.block(Block.DoubleWoodenSlab),
    positions.create(1, 64, 1),
    positions.create(3, 64, 3),
    FillOperation.Replace
    )
}
platform()
```

### Teleport yourself

The last step is to teleport the player to a spot just above the middle of the platform.

17. From `||player:PLAYER||`, drag a `||player:teleport to||` into `||functions:teleport||`.

18. In `||player:teleport to||`, enter the following values for the coordinates: `(2, 65, 2)`.

19. Set the gamemode to survival by going to `||gameplay:GAMEPLAY||` and dragging out a `||gameplay:change game mode to||`.

```blocks
function teleport() {
    player.teleport(positions.create(2, 65, 2))
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.LocalPlayer)
    )
}
teleport()
```

## Give it a try!

Now try out your mini-game!

Find a spot of open ground. Remember, because your game basically starts whenever the `||loops:on start||` loop executes, you might need to start and stop the code to get it to reset for you. Then take a Leap of Faith! Remember that when you are up on the platform, holding down the Shift key while moving around will keep you from falling off while you look for a good spot to jump. Have students try playing each other’s games.

### ~ hint

The `||loops:on start||` block runs when the program starts. This can be a pain at times if you are testing code or want to restart the program. Use the buttons in the lower-left corner to restart your code on these occasions.

1. Click the stop button in the lower-left corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

2. Restart the coding environment. Click the play button. If the play button is not on, then your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

### ~

![Leaping platform](/static/courses/csintro/functions/leap-platform.jpg) It’s a long way down!

![Leaping platform Final](/static/courses/csintro/functions/platformfinal.jpg) On Platform

## Complete Program

```blocks
function pool() {
    blocks.fill(
    blocks.block(Block.Water),
    positions.create(0, -1, 0),
    positions.create(2, -3, 2),
    FillOperation.Replace
    )
}
function teleport() {
    player.teleport(positions.create(2, 65, 2))
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
}
function platform() {
    blocks.fill(
    blocks.block(Block.DoubleWoodenSlab),
    positions.create(1, 64, 1),
    positions.create(3, 64, 3),
    FillOperation.Replace
    )
}
pool()
platform()
teleport()

```

## Challenges

### Challenge 1 - Halloween Platform Jump

Let's make the jump a little more interesting. You can make it more dangerous by changing the water to lava and spawning some monster around the pool. You should equip your character with a weapon too.

See if you can:

1. Change the water to lava.
2. Spawn some monsters next to the pool.
3. Give your character a sword of some kind.

Make new functions that handle the preceding steps 2 and 3. You can call these new functions **Monsters** and **Sword**. You will then need to call these new functions from `||loops:on start||`.

It seems like you would die every time. Is there a way to fix this? Maybe save your character when you fall? You might add water or change the gamemode to make the challenge better.

### Challenge 2 - On Bounce

Did you know you can bounce on slime?

Change water in the original activity to slime! Add a call to a function in a new event, `||player:on player bounce||`. Your function can do whatever you want. The new code would look like this with your idea added to the function.

```blocks
player.onTravelled(TravelMethod.Bounce, function () {
    myNewFunction()
})
function myNewFunction()  {

}
```

## Experiments

### Experiment 1 - Bouncing Pigs

Jumping on slime allows your character to bounce. This code creates slime when you enter **slime** in the chat window. Then you press the spacebar to jump and bounce. Watch it rain pigs!

What other cool things could you make by using slime?

Notice how you have kind of a chain reaction as one function is called and then an event fires and another function is called. Still, it is easier to read with functions!

### Experiment 2 - Bouncing, Lightning, and Zombie Pigmen

This just takes things up another notch from the last experiment!