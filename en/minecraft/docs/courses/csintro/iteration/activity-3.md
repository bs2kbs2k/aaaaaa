# Activity: Help Your Agent Farm

You want to start farming with your robot agent, but you have a few errors in the instructions. Using loops, it would be nice to teach the agent to build a couple of rows of tilled soil where crops could be planted. Can you debug this code and figure out where the problems are?

You have your new garden all planned and need a 2 x 6 plot of perfectly aligned tilled soil. With a couple of `||loops:repeat||` loops, you can get your agent to till this. The issue is that the code in this activity is only partially complete. You will need to go through the activity and fix the broken code at the end.

## Do the activity

### The Basic Setup

1. Let’s start out by creating a new MakeCode project and call it **Farmer**.

2. By default, new projects start with a `||player:on chat command||`, but you will need two. Duplicate this `||player:on chat command||` by right-clicking and selecting duplicate.

3. Name one `"tp"` to teleport the agent to your location, and name the other one `"farm"`.

4. From `||agent:AGENT||`, put `||agent:agent teleport to player||` inside `||player:on chat command "tp"||`.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("farm", function () {
})
```

### Till Some Soil

1. From `||loops:LOOPS||`, drag a `||loops:repeat||` block into `||player:on chat command "farm"||`.

2. This will determine the length of our row, so in `||loops:repeat||` change `4` to `6`.

3. From `||agent:AGENT||`, put an `||agent:agent till||` and `||agent:agent move||` block into `||loops:repeat||`.

```blocks
player.onChat("farm", function () {
    for (let i = 0; i < 6; i++) {
        agent.till(SixDirection.Forward)
        agent.move(SixDirection.Forward, 1)
    }
})
```

### Come Back and Till Another Row

So far, using the current code, the agent will till the soil directly in front of it (with its own diamond hoe) and move forward into that space. It does this six times because of the `||loops:repeat||` loop. Try running the code in Minecraft to see what happens.

![Agent Tills First Row](/static/courses/csintro/iteration/act3-till-first-row.jpg)

Notice where the agent ends up after the `||loops:repeat||` block finishes. This is great, but you need two rows! You need to get the agent to turn around and till the next row over so it ends up like the following picture.

![Agent Tills Two Rows](/static/courses/csintro/iteration/act3-till-2-rows.jpg)

Adding another `||loops:repeat||` block will allow you to accomplish this. You will also need to add some directions to turn the agent around before it starts the next row. Here is our attempt:

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("farm", function () {
    for (let i = 0; i < 2; i++) {
        for (let j = 0; j < 6; j++) {
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        }
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 1)
        agent.turn(TurnDirection.Left)
    }
})
```

If you run this code, you will notice that there is a problem. The agent is not set up properly, and the second row is not aligned. How can you fix the code to make this work properly?

![Agent Tills Two Rows](/static/courses/csintro/iteration/act3-till-2-rows-wrong.jpg)

Again, you want something more like this, where the rows are aligned perfectly. The direction the robot faces at the end is not important.

![Agent Tills Two Rows Perfectly](/static/courses/csintro/iteration/act3-fixed.jpg)

![Agent Tills Two Rows Perfectly From Above](/static/courses/csintro/iteration/act3-fixed2.jpg)

## Challenges

### Challenge 1 - Get Agent to Till Aligned Rows

Get the agent to till aligned rows as discussed earlier. There are a few ways to do this, but try to use the core of the existing code to do it. This means you need to keep the two loops in your answer.

### Challenge 2 - Get Agent to Till a 5x6 Plot of Aligned Soil

Can you change the dimensions of the garden? We need more carrots! Try to make a 5x6 garden instead of 2x6.

There are many ways to do this. Can you figure out a way to do it by adding a third loop? If not, then try another approach. Positioning your agent before each loop starts is the most important thing to consider.

![Agent Tills 5x6 Plot](/static/courses/csintro/iteration/act3-challenge2.jpg)

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given but do as you like!

### Experiment 1 - Creating a Help Menu for Users

Controlling the agent is not easy, and sometimes it is easy to forget all the commands. This code has a built-in Help menu. It takes in commands as integers from 1-6. Entering a '?' gets you help or you can just enter **do** without an integer to get the Help menu.

How can you change this code so it moves the agent forward based on a number the user enters for the `||player:on chat command "do"||`? What if you wanted to enter something like 'do 1 4', for example, to move your agent forward four? Is this possible? What other code could you build a Help menu for?

![Agent Tills 5x6 Plot](/static/courses/csintro/iteration/act3-exp1.jpg)

### Experiment 2 - Creating a Raised Farming Bed with Planted Crops

You can use this code to create a raised farming bed with crops. This is a huge amount of code, but if you look at it block by block, you can probably figure out how it works.

You use functions to organize your code a bit. [Functions](/courses/csintro/functions) are covered in a later lesson, but basically, they are an awesome way to organize your thinking when you code.

Also, you use the builder blocks to construct your raised farming bed. Feel free to play around with these.

Here is how you use this code:

![Menu](/static/courses/csintro/iteration/exp2-menu.jpg)

1. Choose a nice spot for a raised farming bed.

2. Teleport your agent to your character's location (chat command 'do 6').

3. Give your character some seeds (chat command 'do 7').

4. You will need to transfer seeds to the agent's inventory so the robot can access them when it plants. To do this, right-click on your agent. Move your character's seeds to your agent's inventory as shown in the following picture. The seeds must be put in that upper-left box, or the code will not work.

![Move Seeds to Agent](/static/courses/csintro/iteration/exp2-give-seeds.png)

1. Build the raised farming bed (chat command 'do 8').

2. Now you will need to turn your agent so that it is facing you. If you don't turn it correctly, the agent will not plant where you want. Turn the agent to face you as shown in the picture. Chat commands 3-5 allow you to turn the agent easily.

![Turn Agent Towards You](/static/courses/csintro/iteration/exp2-turn-agent.jpg)

1. Plant (chat command 'do 9')!

![Beautiful Finished Garden](/static/courses/csintro/iteration/exp2-finished.jpg)

How would you modify this to make your farming bed bigger? Could you get your agent to plant different crops? What about putting plants in some rows, water in others, and decorative blocks as a third style for rows? What about getting the agent to plant seeds in all the soil in the raised farming bed?