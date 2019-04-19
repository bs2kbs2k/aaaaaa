# Activity: Auto Farmer

In this activity, students will become *farmers* who must herd sheep in Minecraft, but of course they will use a bit of code to make it happen! Let's create some sheep and then *auto* matically put them in their pen.

## Do the activity

### Spawn sheep

1. Create a new MakeCode project called "autofarmer".

2. From `||player:PLAYER||`, get `||player:on walk||`.

3. From `||mobs:Mobs||`, drag `||mobs:spawn||` into `||player:on walk||`.

4. Select the `sheep` or another animal for your farm in `||mobs:spawn||`.

5. Put the coordinates **(~0, ~0, ~1)** in `||mobs:spawn||`. Sheep will spawn one block south of the player along the **Z**-axis.

## ~ hint

**(X):** Distance east or west from the (**0**, 0, 0) world origin, just like in real-world longitude.

* East (+X)
* West (-X)

**(Y):** Distance up or down from the (0, **0**, 0) world origin, just like in real-world altitude.

* Up (+Y)
* Down (-Y)

**(Z):** Distance south or north from the (0, 0, **0**) world origin, just like in real-world latitude.

* South (+Z)
* North (-Z)

## ~

![spawn sheep](/static/courses/csintro/coordinates/spawnsheep.jpg)

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(0, 0, 1))
})

```

## ~ hint

**Clear All Sheep**

If at any time you want to "reset" the situation, you can kill all the sheep and start clean by using this command in the terminal:

    /kill @e
    

This kills all entities.

## ~

### Start the sheep pen - south wall

After spawning several sheep, you now need a place to put them. This is where coordinates will be needed so you can build their pen. You don't want them to get away!

When studying coordinates, you have talked about them as (X, Y, Z) and (east-west, up-down, south-north), BUT you might consider using different words when building this pen. Perhaps this way of thinking might be more natural to you. Let's assume:

* `X` = length 
* `Y` = height
* `Z` = thickness of the pen wall

6. From `||player:PLAYER||`, drag a `||player:on chat command||` to the Workspace and change the command to `"pen"`.

7. From `||blocks:BLOCKS||`, place a `||blocks:fill with||` inside `||player:on chat command "pen"||`.

8. Adjust this to `||blocks:fill with||` `Nether Brick Fence`.

Here you will use different colors for each side of the pen so you can see a little more clearly how your code works.

9. Change the coordinates to those shown in the following code.

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    blocks.block(Block.NetherBrickFence),
    positions.create(5, 0, 1),
    positions.create(-5, 4, 1),
    FillOperation.Replace
    )
})
```

Coordinates (X, Y, Z):

* X = length
* Y = height
* Z = thickness of the pen wall

Your fence extends from 5 to -5 on the X-axis, which is actually 11 blocks because 0 counts as one block >> *Length = 11* Your fence extends from 0 to 4 on the Y-axis, so that is five blocks tall >> *Height = 5* Finally, your fence extends from 1 to 1 on the Z-axis, so it is one block thick >> *Thickness = 1*

## ~ hint

**Relative coordinates**

The tilde (~) means that these coordinates are relative to where you stand in the world. You chose to build the south wall, so you are just on the outside of it when it gets built.

## ~

![fence wall on start](/static/courses/csintro/coordinates/fence_onstart1.jpg)

### Create side walls

When you build the side walls, you need them to line up with ends of your south wall. The south wall's ends are at 5 and -5. You will build side walls that are 20 blocks in length, again with a thickness of one block.

If you use the same reasoning as before when you created the south wall, the pen will not work. The direction of your walls has changed. Because of this change, your X, Y, and Z now represent something different. You still have height, length, and thickness, but now they are ....

Coordinates (X, Y, Z):

* X = thickness of the pen wall (1) >However, this also determines whether the side walls line up with your south wall corner. This coordinate is the most important and is tricky.
* Y = height (5)
* Z = length (20)

The code is almost the same as that for the south wall, except for the coordinates. You will also change materials for each side wall so you can better see what your code is doing. Therefore, let's do this:

10. Right-click the `||blocks:fill with||` block that is making your south wall. Duplicate it twice. These new duplicates will be your side walls.

11. Adjust the material for the side walls. One side can be Acacia Fence, and the other can be Birch Fence.

![select side wall fencing](/static/courses/csintro/coordinates/select-side-wall-fencing.png)

12. Adjust the coordinates as shown in the following code.

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    blocks.block(Block.NetherBrickFence),
    positions.create(5, 0, 1),
    positions.create(-5, 4, 1),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.BirchFence),
    positions.create(-5, 0, 1),
    positions.create(-5, 4, 21),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.AcaciaFence),
    positions.create(5, 0, 1),
    positions.create(5, 4, 21),
    FillOperation.Replace
    )
})
```

![fence side walls](/static/courses/csintro/coordinates/fence_onplayerwalk2.jpg)

### Close the sheep pen - north entrance

Finally, you need to close your sheep pen. Again, this is a bit tricky, but the reasoning is similar to that for your south wall. Test yourself before looking below! Can you figure out what your coordinates might be?

Coordinates (X, Y, Z):

* X = length 
* Y = height
* Z = thickness of the pen wall

Z becomes the most important coordinate to get right so that your pen closes perfectly. Z should be exactly 20 blocks away from your south wall because that is how long your side walls are.

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    blocks.block(Block.NetherBrickFence),
    positions.create(5, 0, 1),
    positions.create(-5, 4, 1),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.BirchFence),
    positions.create(-5, 0, 1),
    positions.create(-5, 4, 21),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.AcaciaFence),
    positions.create(5, 0, 1),
    positions.create(5, 4, 21),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.SpruceFence),
    positions.create(5, 0, 21),
    positions.create(-5, 4, 21),
    FillOperation.Replace
    )
})
```

![pen spawned sheep](/static/courses/csintro/coordinates/addsheet_onplayerwalk_complete.jpg)

**Shared Program:** https://makecode.com/_UJy54M35pHmH

### Try it out!

Go into a world and start walking to create a lot of sheep. Then try to pen as many sheep as possible by entering **pen** in the chat window. You can walk by pressing the `W` key, which is the forward key by default. See how many sheep you can pen. Compete against your friends to pen the most sheep in class!

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Spawn Some Polar Bears Randomly

In this challenge, you test out a new protection system for your player. First you will need some animals to test it out. Spawn some polar bears randomly, but make sure to put them a little bit away from your player so you can get ready. You can use the `||player:on walk||` event or something else if you prefer.

### ~ hint

Do you remember how to use random positions?

### ~

### Challenge 2 - Build a Protective Cage

Now, instead of building a pen to keep the bears in, you will build a cage to keep your player safe. It should be five blocks square around your player and five blocks tall. You can use the `||player:on sneak||` event and any fencing you like.

### ~ hint

To sneak, hold down `Shift` while pressing `W` key.

Next you will need to set the gamemode to Survival to make this interesting.

Enter this in the chat window:

    /gamemode s
    

Finally, make sure your difficulty is not set to Peaceful.

Enter this in the chat window:

    /difficulty n
    

### ~

![polar bears protective cage](/static/courses/csintro/coordinates/polar-bears-cage.jpg)

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Mazebuilder

This is a maze builder. First, enter **ms** in the chat window and then sprint by holding down the `Control` key and pressing `W`.

A maze should build as you run. You could change the colors or experiment with the shapes to make your own maze. What can you create?

![inside maze](/static/courses/csintro/coordinates/inside-maze.jpg)

![looking down on maze](/static/courses/csintro/coordinates/looking-down-in-maze.jpg)