# Activity: Wordsmith

A Minecraft world is full of creativity. In this activity, you will use variables to show your creativity with words. You will join two words together to create a new compound word. By using variables, you can store two words and then - in code - combine them. The cool part will be spelling out your new word in Minecraft.

![writing in the sky](/static/courses/csintro/variables/wordsmith-1.jpg)

## Do the activity

### Make a new project

1. Create a new MakeCode project and name it "Wordsmith."

2. From `||loops:LOOPS||`, drag `||loops:on start||` into the coding Workspace.

3. Open `||variables:VARIABLES||`, and add `||variables:set item||` inside `||loops:on start||`.

4. Click **Advanced** to see the `||text:TEXT||` Toolbox category. Select the `||""||` and place this inside `||variables:set item||`, replacing the number 0. You will set this variable to a string.

5. Use the `||variables:set item||` drop-down list to rename `item` to `word1`.

![rename variable](/static/courses/csintro/variables/rename-variable.png)

6. Right-click `||variables:set word1||` and duplicate it.

7. Put this new duplicate in `||loops:on start||`.

You will need to make a new variable to store `word2`. For this one, you cannot just rename it as you did before.

8. From `||variables:VARIABLES||`, click **Make a Variable** and name it `word2`.

9. Now go back to the second `||variables:set word1||` and change `word1` to `word2` from the drop-down list.

```blocks
let word2 = ""
let word1 = ""
word1 = ""
word2 = ""
```

### Write two funny words!

10. Replace the empty `" "` with some text for `word1`.

11. Replace the empty `" "` with some text for `word2`.

These words can be any appropriate words that mix well. For example, your first word might be "rail" for `||variables:word1||`, and your second word might be "road" for `||variables:word2||`.

```blocks
let word2 = ""
let word1 = ""
word1 = "rail"
word2 = "road"
```

### Print `word1`

12. From `||player:PLAYER||`, drag `||player:on chat command||` into the Workspace. Name the command `mix`.

13. From `||blocks:BLOCKS||`, drag `||blocks:print||` to snap inside `||player:on chat command mix||`.

14. From `||variables:VARIABLES||`, put `||variables:word1||` inside `||blocks:print||`.

15. Change the grass to Redstone Ore.

![select redstone ore](/static/courses/csintro/variables/wordsmith-redstone-ore-search.png)

```blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.create(0, 0, 0),
    CompassDirection.West
    )
})
word1 = "rail"
word2 = "road"
```

### Set up `word2`

As you have done many times, you can use `duplicate` to speed up your build here. Knowing when to utilize `duplicate` can really save you a lot of time.

16. Duplicate `||blocks:print||` `||variables:word1||`.

17. Change this so it prints `||variables:word2||`.

18. Change the grass to Redstone Lamp.

### Fine-tune and test

The coordinates shown in the following code work best and provide you with a nice spacing. You will notice that the **Y** value is a bit positive. You need to print in the air a bit to leave enough room for everything to fit.

Also, you started printing **south** on the **north/south axis**, so...

19. Adjust the `||blocks:print||` so it reads `along South (positive Z)`.

```blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.create(0, 0, 0),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

### A problem

Your two words are now printing, but there is a little problem. If you don't stop moving after typing **mix**, the two words will not be aligned when they print. In the following picture, you can see this little problem on the right.

![a problem](/static/courses/csintro/variables/wordsmith-not-aligned.png)

### Fix it: store your player's world position

You can fix your problem by storing the player's world position when you start to print.

20. From `||variables:VARIABLES||`, click **Make a Variable** and name the new variable `Starting_World_Position`.

21. From `||variables:VARIABLES||`, add `||variables:set item||` to the top of `||player:on chat command mix||`.

22. Change this block to read `Set Starting_World_Position`.

23. From `||player:PLAYER||`, put `||player:player world position||` into `||variables:set Starting_World_Position||`.

```blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.create(0, 30, 0),
    CompassDirection.South
    )
    blocks.print(
    word2,
    blocks.block(Block.RedstoneLamp),
    positions.create(0, 20, 0),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

### Fix the print block's position

Now you want to use the stored world position and change the print block to use this number. The number will be the same, so you don't have to worry about words getting misaligned.

24. From `||positions:POSITIONS||`, drag the following block onto the work area:

![add coordinates](/static/courses/csintro/variables/wordsmith-add-coordinates.png)

This block allows you to add two coordinates together - it is perfect for your purposes. You can add on to the world position you stored before in `Starting_World_Position`.

25. Move stuff around and add things until you get code that looks like the blocks shown here:

```blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.add(
    Starting_World_Position,
    positions.create(0, 30, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    word2,
    blocks.block(Block.RedstoneLamp),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, 0)
    ),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

### Join and print

Finally, you are ready to join these two words together. Again, let's call on our friend `duplicate`!

26. Duplicate one of the `||blocks:print||` blocks and place it at the bottom of `||player:on chat command mix||`.

27. Adjust settings so that you print using `Block of Redstone`.

28. The **Y** relative coordinate should be 5.

29. From the search bar, search for "join". This is a `||text:TEXT||` block.

30. Place this block so `||blocks:print||` reads `print join word1 word2`.

![a new word](/static/courses/csintro/variables/wordsmith-activity-finished.jpg)

```blocks
let word2 = ""
let word1 = ""
let Starting_World_Position: Position = null
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.add(
    Starting_World_Position,
    positions.create(0, 30, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    word2,
    blocks.block(Block.RedstoneLamp),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    word1 + word2,
    blocks.block(Block.RedstoneBlock),
    positions.add(
    Starting_World_Position,
    positions.create(0, 5, 0)
    ),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

### ~

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Display a '+' Sign to Make the Action Look Like a Math Problem

You are doing "word math" in this activity, so let's complete the idea and theme this out! Add a plus sign to the left of the words at the top, just like you would if you were adding two numbers.

![add a plus sign](/static/courses/csintro/variables/wordsmith-plus.jpg)

### Challenge 2 - Add a Line to Finish the Math Equation Look

How could you draw a line under the two words to make it look just like a math problem?

![complete the equation](/static/courses/csintro/variables/wordsmith-2.jpg)

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Flying Letters

Write some letters to birds with this code. A random letter from the alphabet is printed as you fly! Notice that the range is 0 through 25! That's because this is zero-based... it starts with 0 as the first position.

How could you print only vowels? In what other ways could you use a random variable and text to create something?

![Letters for the Birds](/static/courses/csintro/variables/wordsmith-exp1.jpg)

### Experiment 2 - Chopping Up Sentences

You can cut out portions of a string (text) to print.

How could you print out two of these words at a time instead of just one? In what other ways could you use a random variable and text to create something? What about using a different sentence or maybe a paragraph?

![Letters for the Birds](/static/courses/csintro/variables/wordsmith-exp2.jpg)

## Reference examples

### Constructive examples:

* [에이전트 벽 만들기](examples/agent-wall)
* [에이전트 타워 만들기](examples/agent-tower)
* [메가 점프](/examples/mega-jump)
* [토끼 침공](/examples/rabbit-invasion)

### Destructive examples:

* [신뢰의 도약](/tutorials/leap-of-faith)
* [스플리프](examples/spleef) 
* [TNT 스플리프](examples/tnt-spleef)