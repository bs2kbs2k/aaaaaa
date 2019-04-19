# Agent Moves

## Introduction @unplugged

Get your agent to move. In this tutorial you will make some chat commands to have your agent move and turn.

![Make your agent dance!](/static/tutorials/agent-moves.gif)

## Step 1

Place a `||player:on chat command||` block and rename it to **"tp"** (short for teleport).

```blocks
player.onChat("tp", function () {

})
```

## Step 2

Place a `||agent:agent teleport to player||` block inside the `||player:on chat command||` block.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## Step 3

Go to Minecraft, press **t** to open the chat and enter **tp**.

## Step 4

Place a `||player:on chat command||` block and rename it **"fd"**. Place a `||agent:agent move||` block to **move** the Agent **forward** by 5 blocks.

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 5)
})
```

## Step 5

Go to Minecraft and enter **fd** in the chat. Will the Agent move?

## Step 6

Place a new **lt** chat command to turn the Agent **left** using the `||agent:agent turn||` block.

```blocks
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

## Step 7

Place a new **rt** chat command to turn the Agent **right**.

```blocks
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

## Step 8

Go to Minecraft and enter commands `tp`, `rt`, `lt` or `fd` in the chat to control your Agent!