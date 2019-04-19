# Unplugged activity: Simon Says If Then Else

This is quick variation on the Simon Says game to practice conditionals (If, Then, Else statements).

## Simon Says game

### How to play

* Everyone stands up 
* The teacher will say a series of conditional statements – some may just be If... Then..., but some may be IF... Then... Else.
* Students will follow the instructions

Here’s a simple example: The teacher will say “**IF** you have brown hair, **THEN** raise your right hand, **ELSE** sit down.” So, everyone who has brown hair should have their right hands raised, and everyone else should be sitting down.

### Teacher tips

* Lead the activity to practice conditionals with simple instructions, yet visually different physical poses.
* Verify that students have correctly executed the instructions based on the criteria.
* Read the conditional statements slowly and clearly.
* Make sure students understand and are following along with each set of statements.
* Reset the students to normal standing positions between each conditional statement.
* Ask the class for a few volunteers to create their own conditional statements for the rest of the class to follow along.

### Examples of conditional statements

* **IF** your name starts with a ‘J’, **THEN** give me a thumbs up
* **IF** the month of your birthday ends with a ‘Y’ or an ‘R’, **THEN** raise both your arms 
* **IF** you play soccer, **THEN** kick your feet (be careful not to kick anyone)
* **IF** your favorite ice cream flavor is chocolate, **THEN** stick out your tongue, **ELSE** make rabbit ears behind your head
* **IF** you play a musical instrument, **THEN** snap your fingers, **ELSE** whistle
* **IF** your favorite monster in Minecraft is a zombie, **THEN** make zombie noises and movements, **ELSE** jump up and down

### Other example conditions

* Your hair is brown / blond / red
* Your eyes are brown / blue / green
* You are wearing a sweater / shorts / T-shirt / pants / skirt / sneakers / sandals
* It is raining / sunny / cloudy today
* You’ve played soccer / volleyball / football / frisbee in the past month
* You’ve eaten spaghetti / cereal / ham / toast in the past week
* You slept well last night / had a hard time waking up this morning
* Your favorite ice cream flavor is chocolate / vanilla / strawberry / mint / cookie dough
* You have a pet dog / cat / bird
* You have a sister / brother / no siblings

## Types of conditions in MakeCode

MakeCode for Minecraft features a conditional block called an **IF... THEN...** block.

There is also another related block called the **IF... THEN... ELSE...** block.

These blocks are in the `||logic:LOGIC||` Toolbox drawer. These blocks will check to see if a certain condition is true, and if so, then they will perform their operations.

If you click the little plus sign at the bottom of these blocks, you can add more conditions.

![Logic drawer](/static/courses/csintro/conditionals/logic-drawer.jpg)

By default, `||logic:IF||` statements have a hexagon that says "true" in them when you first place them. If you don’t change this, then anything that the "If... Then..." block encloses will run every time. "True" is always true.

```block
if (true) {
    player.say("I will always run!")
}
```

However, you can substitute another block, or a combination of blocks, next to the If. The blocks you use as conditions do not have to be hexagons but ultimately should resolve to true or false.

This example from the `|blocks:BLOCKS||` Drawer tests for a certain type of block at a specific set of coordinates.

```block
if (blocks.testForBlock(blocks.block(Block.Grass), positions.create(0, 0, 0))) {

}
```

In this example, they represent the player’s exact location. This is always going to be false because the player is standing there, so there can not be a block where its head or body is. However, you can specify `~0 -1 ~0` to check the block the player is currently walking on, or even use a Position range to detect the presence of a certain block within a given area.

```block
if (blocks.testForBlock(blocks.block(Block.Bricks), positions.add(
    positions.create(0, -1, 0),
    positions.create(25, -1, 25)
    ))) {

}
```

In this chapter, you’ll explore some of the possibilities that the different conditional blocks provide, by automating some common Minecraft tasks like chopping down trees or mining. You'll also be building things like pyramids and making your code work a bit more intelligently so it responds to what the user inputs. Then you’ll challenge yourself to create your own independent project automating some other Minecraft task of your choice. Let’s go!