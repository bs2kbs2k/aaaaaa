# Activity: How Old Are You?

In this programming activity, students will practice using the Conditional `||logic:if then else||` block in MakeCode. They will code a program that uses a condition to compare their friend's age with their own, and print different messages if they are younger, older, or the same age.

## Do the activity

### Make the project

1. Create a New Project and call it **How Old**.

2. Rename the existing `||player:on chat command "run"||` to `"age"`.

3. Click the Plus **(+)** sign on the `||player:on chat command "age"||` to create a `num1` variable parameter.

4. Rename `num1` to `FriendsAge`. This makes your code more readable. Always use meaningful names when making variables in coding. This makes finding errors more intuitive. You can rename variables from the drop-down menu.

```blocks
player.onChat("age", function(FriendsAge) {

})
```

### Use a conditional

5. From `||logic:LOGIC||`, drag a `||logic:if then else||` inside `||player:on chat command "age"||`.

6. Click the Plus **(+)** sign in the `||logic:if then else||` to create another `||logic:else if||` branch.

### Insert the comparisons

7. From `||logic:LOGIC||`, drag a Less than, `||logic:0 < 0||`, comparison block into the `||logic:if||` slot, replacing `true`.

8. Again from `||logic:LOGIC||`, drag an Equals, `||logic:0 = 0||`, comparison block into the `||logic:else if||` slot.

```blocks
player.onChat("age", function (FriendsAge) {
    if (0 < 0) {
    } else if (0 == 0) {
    } else {
    }
})
```

### Compare with your variable

9. From the `||variables:VARIABLES||` Toolbox drawer, drag two of the `||variables:num1||` blocks into the first slot of each of the Comparison blocks.

10. In the second slot of the Comparison blocks, enter your age (for example, `12`).

```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {

    } else if (FriendsAge == 12) {

    } else {

    }
})
```

### Print blocks for each condition

11. From `||blocks:BLOCKS||`, drag a `||blocks:print "Hello"||`onto your Workspace. Then you can right-click `||blocks:print "Hello"||` and select **Duplicate** to make a copy.

12. Place one in each of your `||logic:if||`, `||logic:else if||`, and `||logic:else||` clauses.

```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "HELLO",
        blocks.block(Block.Grass),
        positions.create(0, 0, 0),
        CompassDirection.West
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "HELLO",
        blocks.block(Block.Grass),
        positions.create(0, 0, 0),
        CompassDirection.West
        )
    } else {
        blocks.print(
        "HELLO",
        blocks.block(Block.Grass),
        positions.create(0, 0, 0),
        CompassDirection.West
        )
    }
})
```

### Print different messages

13. In each `||blocks:print "Hello"||`, type a different message for people who are younger than you, your same age, or older than you.

14. Use the drop-down menu in the `||blocks:print||` blocks to select a different block to use for each message.

15. In all the `||blocks:print||` blocks, set the **Y** coordinate to 10 (so these messages print in the sky).

### Have fun showing the age messages

Have students pair up to run these programs:

* In the Minecraft Game, enter 't' to open the chat window.
* Ask your neighbor their age, and enter 'age x' – where x is your neighbor’s age.
* Look in the sky above you at your message!

![Messages in the Sky - Example 1](/static/courses/csintro/conditionals/act1-result.jpg)

![Messages in the Sky - Example 2](/static/courses/csintro/conditionals/sky-messages.jpg)

### Complete program

```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "Baby",
        blocks.block(Block.SmoothSandstone),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "Coincidence?",
        blocks.block(Block.OrangeTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    } else {
        blocks.print(
        "Grandpa",
        blocks.block(Block.Stonecutter),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    }
})
```

**Shared program:** https://makecode.com/_4R5VTf0bD4AM

## Challenges

Let's change some things to make our own different and unique situations!

### Challenge 1 - Compare Ages and Modify Messages

Rather than compare students at 12 years old, compare students to another age. If you're brave, ask your teacher how old they are and put their age in for comparison. Modify the messages for people who are younger than your new age, the same age, or older than your new age. Finally, modify the blocks that print.

### Challenge 2 - Compare Birthdays

Place in another `||logic:if then else||` to check whether your friend has the same birthday as you.

To do this you will need to take in another variable from `||player:on chat command "age"||`. Using a number variable might be easiest, but you could do this in other ways too.

In the following picture, you can see where you would need to test for the proper month, so put your new `||logic:if then else||` there.

![Put New If Here](/static/courses/csintro/conditionals/act1-challenge2.png)

## ~ hint

Because you are printing two messages, one for saying you are the same age and one for responding to the month, the second printing will not start until the first is finished.

If you print from two blocks of code like this, remember that moving around will most likely affect the position of the second block.

## ~

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Try Other Types of Conversions

Use this experiment to change your weight from pounds (lbs) to kilograms (kg) and vice versa.

If you enter **weight** in the chat window, the code shows you a menu that explains the program.

`||logic:If Statements||` allow you to detect what the user wants to convert to. Also, a `||logic:If Statement||` checks whether it is ok to display an answer message.

How could you change this code so that the output is not in the chat window? Maybe you could print blocks instead as an answer....

What other things could you ask people?

### Experiment 2 - Create Blocks and Items

This code has a menu. Enter **create** in a chat window.

The code accepts the ID for blocks and items.

If the ID is for a block (1 - 255), the block is placed.

If the ID is for an item (256 - 452), the item is equipped to your character.

## ~ hint

Some items or blocks may not appear because they need certain other conditions to be placed, for example, a wall.

## ~