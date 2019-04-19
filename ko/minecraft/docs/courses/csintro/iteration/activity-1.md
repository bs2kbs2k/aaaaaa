# Activity: Introduction to the Agent

For this lesson about loops, you will be using the agent in Minecraft. So you will be learning about loops but also getting familiar with how the agent works.

First, let's talk a little about the agent, and then we'll dive into loops more in the next activity.

The Minecraft agent is a little robot who can carry out the commands you write in MakeCode. This activity will walk you through getting started with the agent.

Alternatively, you can follow the interactive [Agent Moves](/tutorials/agent-moves) tutorial in MakeCode.

![Select Agent tutorial](/static/courses/csintro/iteration/select-tutorial.jpg)

## Do the activity

### Make a new project

1. Create a new MakeCode project.
2. Change the name of the default `||player:on chat command||` block to `"tp"`.

```blocks
player.onChat("tp", function () {})
```

### Teleport the agent

1. From the `||agent:AGENT||` Toolbox drawer, drag an `||agent:agent teleport to player||` block and drop it inside the `||player:on chat command||` block.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

### Move and turn your agent

Now, in Minecraft, when you enter **tp** in the chat window, the agent will teleport directly to your location. You should do this whenever you want to use the agent in a project. You might also want to create some additional basic commands to move the agent around:

```blocks
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

This makes it easier to control the agent precisely. Alternatively, you could always just stand where you want the agent to be and then enter **tp** in the chat window.

### ~ hint

**Agent Direction**

Agent commands are based on which way the agent is facing, not the coordinates that we covered earlier in [Lesson 3](/courses/csintro/coordinates).

### ~

## Challenges

Now you can play around with the agent to see what else it can do!

### Challenge 1 - Make the Agent Fly

The agent can move up and down as well as forward and backward.

Create some additional `||player:on chat command||` commands that will move the agent up and down.

### Challenge 2 - Move Your Agent a Set Distance

Let's give the agent very specific directions for movement. How would you make your agent move forward four spaces, turn right, and then move backward six spaces?

You could do this in many ways. Regardless of how you solve this challenge, it might be easiest to create a new `||player:on chat command||` block and put your solution there.

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Fire Walk... I Said NOW, Agent!

This code will create a fire course for your agent to walk through. Then you can use the `on chat` commands to make the agent move through the course. The movement commands from before have been modified a little so that you can now put numbers into your commands. This was covered back in [Lesson 4: Variables](/courses/csintro/variables).

#### Using the code

1. To get started, enter **course** in the chat window. This creates your fire course.
2. Next, enter **fd 5**, for example, to move your agent forward five blocks. The `around` command spins the agent 180°.

How might you modify this code? Could you change what the course is made out of? Could you add a run-and-jump command for your agent? Could you make a course that requires the agent to move up and down?

Notice that here a block type is stored in a variable!

![fire walk](/static/courses/csintro/iteration/exp-fire-walk-1.jpg)

### ~ hint

**Camera View**

Pressing `F5` on your keyboard changes the view so you can see the agent and the fire course more clearly.

### ~

### Experiment 2 - You Can't Contain This Agent!

This code builds a cage for the agent. Enter **contain** to build a cage, teleport your character into the cage, and teleport the agent into the cage with you. When you teleport out, you have trapped the agent! Or have you? Everybody knows you can't really trap an agent.

The `break` command frees the agent!

How could you modify this? It would be more impressive if the agent destroyed the whole cage. You could teleport the agent underground and have it dig back out. There are tons of possibilities.

![contain agent](/static/courses/csintro/iteration/exp-contain-agent-1.jpg)

![agent breaks free](/static/courses/csintro/iteration/exp-contain-agent-2.jpg)