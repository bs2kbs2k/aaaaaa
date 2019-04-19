# Activity: One Block At a Time

This activity uses examples of looping and iteration to build a tower by using the agent.

It shows a `||loops:for||` loop. Loops allow you to repeat code. The `||loops:for||` loop is special because you can easily monitor each pass through the loop.

Functions, covered in [Lesson 7](/courses/csintro/functions), also allow us to repeat code. Loops are different from functions. Loops repeat code over and over in one specific place, but functions are used to spread repeating code throughout applications. When you learn about functions, try to revisit this idea and make sense of the differences between loops and functions.

This activity about loops aims to help you understand how loops work and how you monitor each pass through a loop.

## Do the activity

### Make a New Project

1. Create a new makecode project.

2. Use this starter code from the [Introduction to the Agent](/courses/csintro/iteration/activity-1) activity. This will allow you to easily position your agent, and then you can adapt some of it to do something new.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})

```

1. You can copy the preceding code by highlighting the code, pressing Ctrl+C to copy, and then pasting (Ctrl+V) the code into the JavaScript side in your code connection.

![Paste Starter Code in Editor](/static/courses/csintro/iteration/act4-javascript.png)

### Getting Ready to Equip the Agent

To get your agent to place things, you first need to equip it with the block or item you want it to place. A chat command could make this a little easier, but in the end, there is no automated way of doing this completely at the time of this publication.

1. From `||player:PLAYER||`, drag a `||player:on chat command||` to the workspace.

2. Rename the command to **givegold**.

3. Go to the Search and find **give**.

![Give Block](/static/courses/csintro/iteration/act4-give-blocks.png)

1. Give yourself blocks, and then equip your agent manually. Change the 'Give' so you are giving your character blocks of gold. The maximum you can hold in one inventory slot is 64, so give your character 64 blocks of gold.

```blocks
player.onChat("givegold", function () {
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.block(Block.GoldBlock),
    64
    )
})  
```

### Equip the Agent

1. Now that you have blocks of gold equipped, you need to equip your agent. Use the `||player:on chat command 'tp'||` to teleport your agent near you or walk over to your agent.

2. Right-click your agent to see the agent's inventory and your character's inventory. Transfer the blocks of gold to your agent.

![Transfer Blocks of Gold to Agent's Inventory](/static/courses/csintro/iteration/act4-give-agent-gold-blocks.png)

### ~ hint

Any item you want the agent to use must be placed in the upper-left corner of its inventory first! That exact place, upper-left corner, is critical! It's the only place it will work.

### ~

### Agent - Make a Small Square

Now that your agent has blocks of gold, it is time to make something. Remember Lesson 2 - Activity 1 - Yellow Brick Road? Let's have the agent make a square for this time that could one day link up to that yellow brick road!

Agents cannot replace blocks, but they are able to destroy things!

Let's destroy the ground and replace those blocks with blocks of gold.

1. First, duplicate `||player:on chat command "fd"||` and rename it **square**. You can duplicate by right-clicking and selecting **duplicate**. 

To make your square, you have to think about what it will take to make it. Start with the big goal and work your way down to the small pieces you need to make that happen. When you start coding, you work on the smallest part first, adding more as you go. The following shows your final goal.

![Our Goal](/static/courses/csintro/iteration/act4-gold-square-preview2.jpg)

Let's start by placing just one gold block to accomplish your goal. What code would you need to do this?

1. From `||agent:AGENT||`, put `||agent:agent destroy down||` inside `||player:on chat command "square"||`.

2. Put `||agent:agent place down||` inside `||player:on chat command "square"||`.

The agent will place whatever is in that upper-left corner of his inventory, like we talked about earlier. It will place the blocks of gold in this case. Now `||player:on chat command "square"||` should look like the following:

```blocks
player.onChat("square", function () {
    agent.destroy(SixDirection.Down)
    agent.place(SixDirection.Down)
})

```

Success! Now let's try to take this a step further. Using a loop, let's try to make one side of the square! You need your agent to move, and you need him to break and place several times. This is a perfect problem for a loop.

1. From `||loops:LOOPS||`, grab a `||loops:repeat||` loop to surround the existing code in `||player:on chat command "road"||`.

2. Adjust the `||loops:repeat||` loop to repeat six times.

3. Adding `||agent:agent move forward by 1||` at the end of this loop will get your agent moving while he destroys and places blocks.

```blocks
player.onChat("square", function () {
    for (let i = 0; i < 6; i++) {
        agent.destroy(SixDirection.Down)
        agent.place(SixDirection.Down)
        agent.move(SixDirection.Forward, 1)
    }
})

```

### Completed Code Up Until This Point

```blocks
player.onChat("square", function () {
    for (let i = 0; i < 6; i++) {
        agent.destroy(SixDirection.Down)
        agent.place(SixDirection.Down)
        agent.move(SixDirection.Forward, 1)
    }
})

player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

## Challenges

Last step... Now we need to repeat this line four times. Can you figure out how to accomplish what's shown in the following picture? Well, besides the water part! You can make your square whereever you want.

![Our Goal](/static/courses/csintro/iteration/act4-gold-square-preview.jpg)

### Challenge 1 - Turn One Line into a Square

What is a square? In this case, let's say four lines. How do you make a square by using the code you have up to this point as a starting place?

### ~ hint

The lesson is about loops, so you might need another, but you will also need one other block.

### ~

### Challenge 2 - Make a Tower

A tower is just several squares laid on top of each other. Can you add yet a third loop to accomplish this?

![A Tower of Gold](/static/courses/csintro/iteration/act4-challenge-2.jpg)

What happens when you try to build a gigantic tower?

![A Tower of Gold](/static/courses/csintro/iteration/act4-challenge-2a.jpg)

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Starter Castle

How far can you go with a loop inside a loop inside a... you get the idea. These are called nested loops, and if you add another with some code, can you make a castle?

Most castles have four towers. With this code you get two. Go get a sandwich while your agent does all the work. After this, you can write code to make it build the other two towers and walls!

![Split Tower](/static/courses/csintro/iteration/experiment1-two-towers.jpg)

What other weird tower designs could you think up? Tinker with the code and make it happen!

![Split Tower](/static/courses/csintro/iteration/experiment1-extra-ideas.jpg)