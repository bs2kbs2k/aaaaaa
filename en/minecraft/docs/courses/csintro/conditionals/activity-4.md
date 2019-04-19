# Activity: Pyramid

In this programming activity, students will try to place conditional `||logic:if||` statements to improve existing code. The starter code you will be working with creates pyramids of various sizes. You premade some controls for your agent, which makes things easier, but some problems with the code cause the actual pyramids to build themselves. Can you help sort out some of these issues and improve the code?

## Do the activity

### Copy the Starter Code

1. Copy the following code to your computer's clipboard by highlighting it and pressing `Ctrl+C` on your keyboard.

```typescript
player.onChat("tp", function () {
    player.teleport(positions.create(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(positions.create(-3, 0, -3))
})
player.onChat("pyramid", function (BaseSize) {
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, BaseSize - 1)
        agent.turn(TurnDirection.Left)
    }
    agent.move(SixDirection.Up, 1)
    agent.setAssist(AgentAssist.PlaceOnMove, false)
    agent.move(SixDirection.Forward, 1)
    player.runChatCommand("pyramid " + (BaseSize - 2))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
```

1. In the block editor, change to the JavaScript view.

![Paste in Javascript](/static/courses/csintro/conditionals/act4-javascript.png)

1. Select everything already there (press Ctrl+A) and delete it. Then paste your starter code into this window (Ctrl+V).

![Pasted Code in Javascript](/static/courses/csintro/conditionals/act4-javascript-pasted.png)

### Examining the Problem with the Starter Code

If you run this code just the way it is, you will notice something peculiar. Try it out!

1. Equip your agent with some blocks. This was covered before, but in case you forgot or did not catch it the first time, read the tip below.

### ~ hint

To give your agent something to place, go over to your agent and right-click it. Move some blocks from your character's inventory to your agent's inventory as shown in the following picture. The blocks must be put in that upper-left box or the agent will place nothing.

![Equip Agent with Blocks](/static/courses/csintro/conditionals/act4-give-agent-gold-blocks.png)

### ~

1. In your chat window, enter **tp** to teleport your agent near you. You may want to turn your agent by using the Turn command as well, but perhaps this is not necessary.

2. Enter **pyramid 5** in the chat window and see what happens.

Your agent should build the pyramid just fine, but it will not stop there. The agent just keeps building and building forever. Your code is in an infinite loop!

This happens because at the very end of the code, you have a block that continues to call the code again and again.

```blocks
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```

Your task is to put some If statements into this code to stop the infinite behavior!

![Infinite Loop](/static/courses/csintro/conditionals/oops-beg.jpg)

1. Use the following tip to stop the infinite loop so you can get to work!

### ~ hint

If you are caught in an infinite loop, you will need to stop your code from the code connection window.

1. Click the stop button in the lower-left corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

1. Restart the coding environment. Click the play button. If the play button is not on, then your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

1. Saving your code again can restart your code, so let's do that for good measure. Save one more time and say **yes** to the warning message. 

![Save](/static/courses/csintro/conditionals/save.png)

![Save Confirm](/static/courses/csintro/conditionals/save-override.png)

### ~

### Stop Looping

To stop the loop, you need to check a variable and then tell your code to stop the loop. Using an **if** statement is great in this kind of situation.

1. From the `||logic:LOGIC||` Toolbox drawer, drag a `||logic:if then else||` block into your code so that the **if** statement surrounds all the code inside `||player:on chat command "pyramid"||`.

```blocks
player.onChat("pyramid", function (BaseSize) {
    if (true) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        for (let i = 0; i <= 3; i++) {
            agent.move(SixDirection.Forward, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

Now let's enter the condition. You want the loop to stop if the size goes below zero. The user enters a size and after each pass through this code, the size gets reduced by `2`. Again, this block is where that is happening...

```blocks
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```

1. From `||logic:LOGIC||`, grab one of the blocks in the following picture and place this inside your `||logic:if then else||`.

![Check the Size](/static/courses/csintro/conditionals/comparisons.png)

You want your comparison to read `'BaseSize > 0'`. If the size is greater than zero... let's build something BUT if it is not, you will give the user a message.

```blocks
let MadePyramid = false
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(SixDirection.Forward, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

With that If statement, you stopped the looping!

![Red Pyramid](/static/courses/csintro/conditionals/red-pyramid.jpg)

How else could you improve this code? There are two situations where the size will be zero:

**A.** The agent has just finished building a pyramid.

**B.** The user forgot to enter a size for their pyramid.

The code will go to this point when that happens.

![2nd If](/static/courses/csintro/conditionals/act4-where-to-put-2nd-if.png)

Can you figure out a way to check for the preceding two conditions (A and B)? You would check for this in that else branch....

Look closely at our final code before doing the challenges. There is a hint to how to solve this puzzle.

```blocks
let MadePyramid = false
// Teleports the agent near you but a little away so
// you have time to get out of his way when he starts
// building
player.onChat("tp", function () {
    player.teleport(positions.create(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(positions.create(-3, 0, -3))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(SixDirection.Forward, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

Did you notice this new block?

![Hint - New Variable](/static/courses/csintro/conditionals/set-made-pyramid.png)

Try using this variable and a `||logic:if||` statement to complete the challenges!

## Challenges

Let's change some things to make our own different and unique situations!

### Challenge 1 - Tell the User When the Pyramid Is Built

Using a `||logic:if||` statement, tell the user when the pyramid is done.

Using the variable `MadePyramid` might help.

In your message, you might say something simple like "Pyramid Done!" or you can get more creative with it.

### Challenge 2 - Say Something If the User Enters 0 or No Size Is Entered

Try to get the code to inform the user if they entered 0. There is a trick to this that you might have overlooked in Challenge 1. It has to do again with the variable `MakePyramid`.

Again, you can be creative with your message here, but usually giving an example of what to enter is helpful. Something like this:

    To make a pyramid enter a size >> Example - "pyramid 5"
    

![Enter a Size](/static/courses/csintro/conditionals/act4-challenge2.jpg)

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Wander

The agent randomly walks around leaving a trail of blocks. You can run this script a few times to create abstract art in the world.

How might you also make the agent move up and down randomly?

### Experiment 2 - Build a Colorful Pyramid into the Side of a Hill

This script gets your agent to build pyramids while destroying blocks that are in the way. You will need to equip your agent with at least nine types of blocks.

In case you forgot... to equip blocks, right-click your agent and move blocks over to its inventory. Fill up that top row!

![Build Pyramid Into a Hill](/static/courses/csintro/conditionals/Load-up-agent-inventory-9-slots.jpg)

![Build Pyramid Into a Hill](/static/courses/csintro/conditionals/build-pyramid-into-hill-best.jpg)

![Pyramids Everywhere!](/static/courses/csintro/conditionals/build-pyramid-into-hill-best2.jpg)

See what other structures you might build with this concept. You could get an agent to build you a gold lined cave! You might make a super high pyramid. Try to figure out how to build an upside-down pyramid.