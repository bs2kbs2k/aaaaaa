# Activity: Minecraft Moving Company

![selected Minecraft object](/static/courses/csintro/coordinates/selected-object.jpg)

If you’ve ever built the perfect house in Minecraft but wished you had done it in a different location, now you can! You can use coordinates and some of the block operations in the `||blocks:BLOCKS||` Toolbox drawer to copy and paste entire portions of the Minecraft landscape. You can copy hillsides, lakes, and even entire buildings! Let’s create a way to specify an area of the world, then copy it somewhere else.

In this project, you will use three different `||player:on chat command||` commands:

* `"start"` : This sets one corner of the area to be copied.
* `"stop"` : This sets the opposite corner of the area to be copied.
* `"copy"` : This creates an exact copy of everything between the start and stop points, placing it at your current position.

## Do the activity

### Make the chat commands

1. Create a new MakeCode project called "Move Me" or something similar.

2. Drag three `||player:on chat command||` blocks into the coding Workspace.

3. Change the name of these `||player:on chat command||` blocks to `"start"`, `"stop"`, and `"copy"`.

```blocks
player.onChat("start", function () { })
player.onChat("stop", function () { })
player.onChat("copy", function () { })
```

### ~ hint

There is a faster way to create three similar blocks. Do you know how? This is introduced in detail later in this activity.

![Duplicate](/static/courses/csintro/coordinates/duplicate.png)

### ~

### Create the variables

Let’s create some variables that you’ll use to store the starting and stopping positions. Variables are covered in detail in [Lesson 4](/courses/csintro/variables), but for now just note that you will use one variable to store the (X, Y, Z) location for the bottom corner of the box and a second variable to store the location of the top corner.

4. Open `||variables:VARIABLES||` and click the **Make a Variable** button.

![Make Variable Button](/static/courses/csintro/coordinates/make-variable-button.png)

5. Name the variable **start**, and click **Ok**.

![Name Variable Start](/static/courses/csintro/coordinates/name-variable-start.png)

### Make another variable

6. Click the **Make a Variable** button again.

7. Name the second variable **stop**, and click **Ok**.

### Set the variables

Now let’s set the value of these variables based on the player’s current world position.

8. From `||variables:VARIABLES||`, place a `||variables:set||` variable block into `||player:on chat command||` for `start`.

9. Use the drop-down menu and adjust this to say `||variables:set start||`to `0`.

10. Adjust `0` to `||player:player world position||`. From `||player:PLAYER||`, drag `||player:player world position||` into `||variables:set start||` and replace the `0`.

```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
})
```

### Print messages

Let’s print out a message that displays the coordinates you saved as the starting position.

11. Open `||player:PLAYER||`, and add `||player:say||` after `||variables:set start||`. 

```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Hi!")
})
```

12. Click the **Advanced** tab in the Toolbox to expand the Toolbox categories.

![Text drawer](/static/courses/csintro/coordinates/text-drawer.jpg)

13. Open `||text:TEXT||`, and place `||text:join||` into the `||player:say||` block, replacing `"Hi!"`.

14. In the first slot of `||text:join||`, enter **"Starting Point Set: "**.

15. Next, open `||variables:VARIABLES||`, and drag `||variables:start||` into the second slot of the `||text:join||` block.

```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})
```

### Repeat for the stop command

The code for the stop position is very similar, so to create this you will duplicate the blocks inside `start` and just change the new copy a little. This will save you a lot of time. You can right-click any block and select **Duplicate** to copy blocks. This is a good strategy that speeds up your workflow when you are creating large blocks of similar code!

16. Right-click `||player:on chat command||` `"start"` and duplicate it.

Now you might be able to see that you could have started this activity in a completely different way. Because you can duplicate, you did not really need to drag three `||player:on chat command||` blocks to the Workspace as step 2 instructed. You could have just waited and duplicated. Let's try this a different way.

### ~ hint

There is no "one way" to code. That's what makes coding fun. However, there are faster and more efficient ways to get to the same answer. As your coding skills get better and better, challenge yourself to think of new and faster ways to accomplish the same goals!

### ~

17. Delete the empty `||player:on chat command||` blocks for `"stop"` and `"copy"`.

Let's just duplicate `"start"` two times and change things as needed. `"stop"` will be very similar to `"start"`, so just change the inside blocks of the duplicate as necessary.

```blocks
let stop: Position = null
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```

For `"copy"`, you can delete the inside blocks and rename the duplicate. In the end, you should get something that looks like the blocks shown here:

```blocks
let start: Position = null
let stop: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting point set" + start)
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping point set" + stop)
})
player.onChat("copy", function () {

})
```

### Build the copy command

Now that you’ve set the starting and stopping points, you will create the ability to copy the area in between these points.

18. Open `||blocks:BLOCKS||`, and drag the first `||blocks:clone||` block (the one with the mask property) into `"copy"`. This block clones, or copies, the area from the first set of coordinates to the second set of coordinates. It also copies it into the third set of coordinates.

```blocks
player.onChat("copy", function () {
    blocks.clone(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

19. From `||variables:VARIABLES||`, drag `||variables:start||` into the first slot in `||blocks:clone||`. Your block should now read `clone from start`.

20. From `||variables:VARIABLES||`, drag `||variables:stop||` into the second slot in `||blocks:clone||`. Your block should now read `clone from start to stop`.

```blocks
let start: Position = null
let stop: Position = null
player.onChat("copy", function () {
    blocks.clone(
    start,
    stop,
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

### Test the code

Now let’s test out the code.

![selected Minecraft object](/static/courses/csintro/coordinates/selected-object.jpg)

21. Enter into a Minecraft world where you have a house or some other structure you want to copy.
22. Move your player to one of the bottom corners of the structure, and in the chat window, type the command **"start"**.
23. Move your player diagonally to the top corner from the start. In the chat window, type the command **"stop"**.
24. Move your player to an open space in the world where you want to copy the structure, and in the chat window, type the command **"copy"**.

Did it copy your house or structure correctly?

### ~ hint

**Notes**

* If you can, leave a block or two of space between your character and the object you are copying. That way you will not cut it off.
* For fun, cut some objects in half!!
* The orientation of whatever you copy will always be the same. For example, if a building faces east, it is always going to face east.
* In the `clone` block, for the `mode` property, if you choose `move` instead of `normal`, the code will perform a cut and paste rather than a copy and paste. It will delete what was in between the old coordinates and paste a copy at the new coordinates.

### ~

### Complete program

```blocks
let stop: Position = null
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})
player.onChat("copy", function () {
    blocks.clone(
    start,
    stop,
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```

**Shared Program:** https://makecode.com/_dHhhCoW85JAJ

Copy the wagon from the Oregon Trail World:

![Oxen for an Oregon train wagon](/static/courses/csintro/coordinates/wagon-oxen.jpg)

Set the starting point at the lower-left corner.

![Oregon train wagon without oxen](/static/courses/csintro/coordinates/trail-wagon.jpg)

Set the stopping point at the upper-right corner.

![Oregon train wagon with oxen](/static/courses/csintro/coordinates/trail-wagon-with-oxen.jpg)

Copy somewhere else!

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Cut and Paste Structures

How would you move something instead of copying it? Play around with the settings of the `||blocks:clone||` block to make this possible. Then rename your `||player:on chat command||` to `"cut_paste"`.

### Challenge 2 - Move Only the Tree Trunk

How would you implement a cut and paste special? Is there a way to cut only certain blocks from an area?

Let's try to cut only the trunk from a tree.

Can any of the settings in `||blocks:clone||` help you? See if you can figure out how!

### ~ hint

Did you notice that there are two kinds of `||blocks:clone||` blocks?

### ~

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Walk Through Walls

Can you identify the coordinates in this code?

As a challenge, replace blocks around your character with air blocks. This will make it look as if things around you are disappearing. You can walk through things!!! The air blocks should be four blocks wide, three blocks high, and two blocks in front and behind the player. Try to walk through massive structures, like mountains! You could replace some blocks with air and some with diamonds to create a diamond tunnel everywhere you walk. What other ideas can you come up with?

By playing with the coordinates, you can come up with some pretty interesting situations.