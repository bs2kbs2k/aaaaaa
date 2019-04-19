# Agent Build

## Introduction @unplugged

The agent is very useful if it can build things for you. One thing you will learn in this tutorial is how to use the `||agent:agent place on move||` block. This tells your agent to place a block every time it moves. You will make some chat commands to tell the agent to place blocks and to move forward. You will also add some commands for turning your agent. With these commands you can make your agent build a shape. In this tutorial, the shape is a square.

![The agent can build things for you](/static/tutorials/agent-build.gif)

## Step 1

Go to your Agent in Minecraft and equip him with blocks. Can't find your Agent? Add a chat command with the `||agent:agent teleport to player||` block.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## Step 2

Add a new chat command **pd** (for "**p**en **d**own") and place a `||agent:agent place on move||` block to tell the Agent to place a block as it moves.

```blocks
player.onChat("pd", function () {
    agent.setAssist(AgentAssist.PlaceOnMove, true)
})
```

## Step 3

Add a chat command **fd** (for "**f**orwar**d**") that **moves** the Agent by `3` blocks.

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 3);
})
```

## Step 4

Go to Minecraft, press **t** to open the chat. Enter **pd** then enter **fd** to get the Agent to build a wall.

Make sure to press **Enter** in the chat after each command.

## Step 5

Add a chat command to build a **square** by combining `||agent:agent move||` and `||agent:agent turn||` blocks.

You can create a sequence of commands that the Agent will execute in order. Try to decompose the different steps, **move** or **turn** needed to build a square.

```blocks
player.onChat("square", function () {
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
});
```

## Step 6

That was an awful lot of blocks! Use the `||loops:for||` block to repeat code.

The `||loops:for||` block tells the computer to repeat the code under it.

```blocks
player.onChat("square", function () {
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
});
```

## Step 7

Ouch the Agent keeps hitting the last block! Use the `||agent:agent detect||` and `||logic:if||` blocks to move up if a block is in the way.

The `||logic:if||` block runs the code under `||logic:then||` if that `||agent:agent detect||` returns **true**.

```blocks
player.onChat("square", function () {
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            agent.move(SixDirection.Up, 1)
        }
    }
});
```