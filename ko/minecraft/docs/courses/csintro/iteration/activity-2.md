# Activity: Dance Dance Agent

In this activity, you’ll create a unique dance for the agent to do, using `||loops:repeat||` loops and `||loops:for||` loops. First, you will make one full sequence of moves, and then use the loops to repeat your dance as many times as you want.

Dancing is a perfect example for loops because when you dance, you often repeat the same moves.

In the `||agent:AGENT||` Toolbox, you will see the following commands:

```blocks
agent.move(SixDirection.Forward, 1)
agent.turn(TurnDirection.Left)
```

You can select a different direction for each of these commands by choosing from the drop-down menu. The `||agent:agent move||` command moves the agent in the direction the agent is facing.

`||agent:agent turn||` turns the agent. This can be used multiple times to spin the agent around 360 degrees.

There are also additional actions for the agent. At the end or start of these actions, the agent does an animation. These might be interesting to add to your dance.

```blocks
agent.till(SixDirection.Forward)
agent.attack(SixDirection.Forward)
```

You have the moves; now you just need to mix them together! Feel free to mix some of those commands in to make your dance more interesting.

## Do the activity

### Make the *"dance"* command

1. From `||player:PLAYER||`, drag a new `||player:on chat command||` block to the coding Workspace.

2. Name this command `"dance"`.

3. Create a sequence of moves for your agent to follow. Here is one example:

```blocks
player.onChat("dance", function () {
    agent.move(SixDirection.Left, 1)
    agent.attack(SixDirection.Forward)
    agent.move(SixDirection.Right, 1)
    agent.move(SixDirection.Right, 1)
    agent.move(SixDirection.Right, 1)
    agent.turn(TurnDirection.Left)
    agent.move(SixDirection.Left, 1)
})
```

### Dance again and again

1. From the `||loops:LOOPS||` Toolbox drawer, drag a `||loops:repeat||` block into the `||player:on chat command "dance"||` block and surround the agent blocks.

```blocks
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
```

1. Use the `||loops:repeat||` block to repeat your sequence of dance moves as many times as you want. 

### Where is your agent?

Last, you need to get your agent to your character so you can see your robot dance. Remember, you can teleport your agent. Let's make a separate `||player:on chat command||` to get your agent.

1. From `||player:PLAYER||`, drag a new `||player:on chat command||` block to the coding Workspace.

2. Name this command `"tp"`.

3. From `||agent:AGENT||`, put `||agent:agent teleport to player||` inside `||player:on chat command "tp"||`.

Then go into Minecraft. First, teleport the agent to your location by entering **tp** in the chat window. Then make him dance by entering **dance** in the chat window!

### ~ hint

**Slo-Mo**

Because the agent moves through the dance steps so quickly, it may be hard to see his dance routine. MakeCode has a *Slo-Mo* feature that allows you to slow down a program so that you can move step by step through each instruction as it is carried out. This is very helpful when you are trying to troubleshoot code or watch a robot dance!

The **Slo-Mo** button is at the lower left of the MakeCode screen and has an icon of a snail on it. When you click to toggle it on, the button turns yellow. Now, when you run a MakeCode program, everything will run slowly. You should be able to see each instruction highlighted in the coding Workspace as the robot carries it out in Minecraft.

![Slo-Mo button](/static/courses/csintro/iteration/slo-mo-button.jpg)

Also, changing your view with **F5** may make the dance more visible.

### ~

```blocks
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})

```

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - A Second Repeat Loop

Recall that `||loops:LOOPS||` are great for things that repeat. In the dance above, you use one `||loops:repeat||` loop, but actually there is a place in the code where you could use a second `||loops:repeat||` loop.

### ~ hint

You would repeat this new loop three times.

### ~

### Challenge 2 - Adding a 3, 2, 1 Start

This challenge will test your learning of variables and loops. Hopefully, you can remember some of those concepts, but go back to review Lesson 4: Variables if needed.

Your challenge is to create a loop that will display a 3, 2, 1 message before the robot starts dancing.

To do this, you would need to:

1. Create a variable that you will change from 3 to 2 to 1.

2. Use a `||loops:loop||`.

3. Use `||player:say||`.

### ~ hint

The `||player:say||` block will accept only strings, but your variable will be a number. You need to cast (change) your number into a string. If you don't, you will get this error:

![Cast Number to a String ERROR](/static/courses/csintro/iteration/act2-challenge2-tip2.png)

Therefore, use `||text:join||` like this:

![Cast Number to a String](/static/courses/csintro/iteration/act2-challenge2-tip.png)

### ~

![Countdown to Dance Revolution](/static/courses/csintro/iteration/activity2-challenge2.jpg)

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - You Dance When I Say

In this code, you use different kinds of loops to stop and start the robot dancing whenever you want. You might use the same structure to start the robot digging, collecting, or doing anything you want. Give it a try!

### Experiment 2 - Instant Dance Floor

This code uses two functions to make a random dance floor. You will also use a bit of teleporting trickery. First, you teleport your character, and then you teleport the agent. Finally, you teleport your character back to its original spot.

How could you change this code? How could you use the two functions that make random blocks in a different way? Could you add even more to set the mood for a dance contest? Night time? Lights?

Could you find a way to keep the robot on the dance floor no matter what dance moves he does?

![Your Robot Dance Floor](/static/courses/csintro/iteration/act2-exp2-1.jpg)

![The Start of a Giant Quilt?](/static/courses/csintro/iteration/act2-exp2-2.jpg)