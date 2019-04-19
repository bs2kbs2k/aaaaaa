# Ratios and gameplay

Students learn different ratio rules for a specific type of gameplay in Minecraft and ensure that their code abides by those rules.

## Learning objectives

Understanding the importance of ratio as it applies to gameplay within Minecraft, and understanding how to refine ratio within a function.

## ~ hint

#### Applicability

**Skill areas**: Math, Ratio, Proportions

**Ages**: 11-12 yrs old

**Grade level**: 6th

## ~

## Guiding ideas

Understand the concept of a ratio and use ratio language to describe a ratio relationship between two quantities.

#### Related Common Core math standards:

* [CCSS.MATH.CONTENT.6.RP.A.1](http://www.corestandards.org/Math/Content/6/RP/A/1)

## Student activities

This activity requires students to have the *Code Connection* app open and running along with their *Minecraft Education Edition*.

This activity consists of 2 parts:

* [Understanding Existing Ratios in Minecraft](#existing-ratios-in-minecraft)
* [Defining Your Own Ratios in Minecraft](#defining-your-own-ratios)

### Existing Ratios in Minecraft

Lead a class discussion about ratios, focus on real-world examples such as 1 car has 4 wheels. Come up with a list of real-world examples on the board.

Have students explore their Minecraft world to discover ratios within Minecraft.

As an example: *One fishing rod is made from 3 sticks and 2 strings.*

Come up with a list of Minecraft ratio examples on the board.

### Defining Your Own Ratios

Have students get into groups of 2 or 3 and create their own new ratios for Minecraft. Lead them through the following example first. The ***italicized*** text is what is told to students.

***To make jumping more interesting, we’ve defined a new jump command that has a ratio of 1:5. For every 1 time jump is called, the player moves up 5 blocks:***

```blocks
player.onChat("jump", function () {
    player.teleport(positions.create(0, 5, 0))
})
```

Walk students through changing the 5 to other numbers and predicting what the ratio would be. Compare this jump command to the way the player jumps in Minecraft naturally (for each space bar press, there is a 1:1 ratio of number of blocks the player jumps).

***You can even make a variable ratio, meaning whatever parameter number you put in, the player will jump that many blocks high:***

```blocks
player.onChat("jump", function (num1) {
    player.teleport(positions.create(0, num1, 0))
})
```

Walk students through the concept that there are two ratios here: 1:*num1* for each time jump is called, the player will go up *num1* of blocks. 1:1 the number that is passed in is exactly how many blocks the player will move up.

Ask students to define their own ratios using [parameters](/reference/player/run-chat-command-with-args) and [loops](/blocks/loops).

## Performance Expectations

#### Intended outcomes:

* This exercise can be completed in one class session depending on the experience your students have with Minecraft and the amount of exploratory time given.
* Students should be able to recognize ratios in the real-world and game-worlds.
* Students should be able to make decisions on creating new ratio rules for real-world inventions or game-world gameplay.