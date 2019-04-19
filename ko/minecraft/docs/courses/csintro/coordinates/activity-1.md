# Activity: Create a Compass Rose

Students will practice using coordinates in Minecraft to create a simple *compass rose* that points to the four cardinal directions within a Minecraft world. Students can then use this as the basis for creating more individualized and detailed compass roses.

## Do the activity

### Make a chat command

1. Create a new MakeCode project called "Compass Rose."

2. From `||player:PLAYER||`, drag a `||player:on chat command||` block out and change the command to `"compassrose"`.

```blocks
player.onChat("compassrose", function () { })
```

### Fill an axis

3. Next, from `||blocks:BLOCKS||`, place a `||blocks:fill with||` block inside the `||player:on chat command||` block.

4. Adjust the `||blocks:fill with||` block from grass to whatever you want the axis to be. The example here uses gray wool for the axis.

5. Put the values `(~-10 ~-1 ~0)` in `from` and `(~10 ~-1 ~0)` in `to`. This will print out a line of 21 blocks along the **X**-axis. The line will be under your feet, and you will be in the very center.

### ~ hint

The reason there are 21 blocks is because in Minecraft, `0` is also a place where you can put a block. So, `0` is included in the 21 places to put blocks.

### ~

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.Grass),
    positions.create(-10, -1, 0),
    positions.create(10, -1, 0),
    FillOperation.Replace
    )
})
```

### Print east and west directions

In `||blocks:BLOCKS||`, you will find `||blocks:print||`. This prints words with any block you choose along a specified axis.

6. Drag out two `||blocks:print||` blocks and place them after `||blocks:fill with||`.

7. Enter **"W"** in the first `||blocks:print||` and **"E"** in the second `||blocks:print||` to indicate west and east.

8. Select a block to `||blocks:print||` the letters in. In this example, lime wool is used for west and yellow wool for east.

9. In `||blocks:print||` `"W"`, enter `(~-11 ~0 ~0)`..

10. In `||blocks::print||` `"E"`, enter `(~11 ~0 ~0)`.

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(-10, 0, 0),
    positions.create(10, 0, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.LimeWool),
    positions.create(-11, 0, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.YellowWool),
    positions.create(11, 0, 0),
    CompassDirection.West
    )
})
```

### Repeat for north and south

Repeat steps 3 through 10, this time for the north-south axis of the compass rose:

11. From `||blocks:BLOCKS||`, place a `||blocks:fill with||` into the `||player:on chat command||`.

12. Adjust the `||blocks:fill with||` block from grass to whatever you want the axis to be. This example uses black wool for the axis.

13. Put the values `(~0 ~-1 ~-10)` in `from` and `(~0 ~-1 ~10)` in `to`. This will print out a line of 21 blocks along the **Z**-axis.

14. Drag out two `||blocks:print||` blocks and place them after the newest `||blocks:fill with||`.

15. Enter **"N"** in the first `||blocks:print||` block and **"S"** in the second `||blocks:print||` block to indicate north and south.

16. Select a block to `||blocks:print||` the letters in. This example uses blue wool for north and red wool for south.

17. In `||blocks:print||` `"N"`, enter `(~0 ~0 ~-11)`.

18. In `||blocks:print||` `"S"`, enter `(~0 ~0 ~11)`.

### Complete program

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(-10, -1, 0),
    positions.create(10, -1, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.LimeWool),
    positions.create(-11, 0, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.YellowWool),
    positions.create(11, 0, 0),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(0, -1, -10),
    positions.create(0, -1, 10),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    blocks.block(Block.BlueWool),
    positions.create(0, 0, -11),
    CompassDirection.West
    )
    blocks.print(
    "S",
    blocks.block(Block.RedWool),
    positions.create(0, 0, 11),
    CompassDirection.West
    )
})
```

**Shared Program:**

Go into a Flat World in Minecraft and enter **compassrose** in the chat command line. For best results, have your player stand still while the letters are being drawn – remember, the positions are being calculated relative to you as the player, so if you move around, the letters will show up in different places!

![compass rose](/static/courses/csintro/coordinates/compass-rose.jpg)

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Create a Bigger Compass

Extend the axis of your compass rose to 41 blocks long. Can you get the letters to print nicely on the end of this new, bigger compass rose?

![compass rose extended](/static/courses/csintro/coordinates/compass-rose-extended.jpg)

### Challenge 2 - Build an Air Compass

Add an up-and-down **Y**-axis and labels. Make your compass up in the sky, so you can look up and see it as you walk along.

What you will need to do:

1. First, you need to move the regular compass into the sky. What coordinate (X, Y, or Z) would you change?
2. Next, you need to build an axis for Y. How could you copy existing code, change it a little, and accomplish that?
3. Finally, print out the words "up" and "down." 

### ~ hint

When you print out the words "up" and "down," move them a little forward (north/south) and a little sideways (east/west). If you don't, the words might cut into your Y-axis.

### ~

![compass rose in the sky](/static/courses/csintro/coordinates/compass-rose-sky.jpg)

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Use Color for Directions

Instead of using **Gray Wool** to print out a line of blocks along the **X**, **Y**, and **Z** axes, you can select different colors to represent the three different directions.

What else might you add to make this more entertaining? What if chickens appeared after blocks? Chickens running along the east/west axis might be interesting. Could you somehow make arrows instead of just straight lines?

### Experiment 2 - Use Colors to Represent Other Compass Features

How about changing the colors of the printed text to the colors of the X, Y, and Z axes? You could change all the colors to something else. You could theme this out a little - make the compass in wood and then use stone and other items to give this compass a medieval theme. How would you theme it?

What if instead of creating a theme you change the code so the **Y**-axis goes up all the way from the ground like a tower?