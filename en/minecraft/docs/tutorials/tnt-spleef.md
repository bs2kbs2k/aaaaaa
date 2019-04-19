# TNT Spleef

## Introduction @unplugged

This should be a blast. Let's make a simple game to give all players TNT and see who can blow things up first. The mod will teleport everyone to the game platform and give each player some TNT. Then, after you enter the chat command, place the TNT and watch out!

## Step 1

Get the [`||player:on chat command||`](/reference/player/on-chat-command) block and rename it to **"bomberman"**.

```blocks
player.onChat("bomberman", function () {
})
```

## Step 2

Place a [`||blocks:fill||`](/reference/blocks/fill) block inside to create a 20x20 layer of **bedrock** at altitude 50.

```blocks
player.onChat("bomberman", function () {
    blocks.fill(
        Block.Bedrock,
        positions.create(0, 50, 0),
        positions.create(20, 50, 20),
        FillOperation.Replace
    )
})
```

## Step 3

Go to Minecraft, press **t** to open the chat and enter **bomberman**. You should see a layer of bed rock on top of your head.

## Step 4

Put in another [`||blocks:fill||`](/reference/blocks/fill) to add a layer of **redstone torch**. Test your code in Minecraft.

```blocks
    blocks.fill(
        blocks.block(Block.RedstoneTorch),
        positions.create(0, 51, 0),
        positions.create(20, 51, 20),
        FillOperation.Replace
    )
```

## Step 5

Get one more [`||blocks:fill||`](/reference/blcoks/fill) block to add a layer of **dirt** on top of **redstone torch**. Test your code in Minecraft.

Placing any TNT on the dirt will ignite it.

```blocks
    blocks.fill(
        blocks.block(Block.Dirt),
        positions.create(0, 52, 0),
        positions.create(20, 52, 20),
        FillOperation.Replace
    )
```

## Step 6

Teleport all the players on top of the platform. Add a `||mobs:teleport to||` block to the end. Test your code in Minecraft.

```blocks
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(10, 55, 10)
    )
```

## Step 7

Give all the players **TNT** blocks to let them play the game. Include a `||mobs:give||` block.

```blocks
    mobs.give(mobs.target(TargetSelectorKind.AllPlayers), Block.TNT, 64)
```

## Step 8

Change the game mode of all players to `survival` so that the game can start! At the end, put a `||gameplay:set game mode||` block.

```blocks
player.onChat("bomberman", function () {
    blocks.fill(
        Block.Bedrock,
        positions.create(0, 50, 0),
        positions.create(20, 50, 20),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.RedstoneTorch),
        positions.create(0, 51, 0),
        positions.create(20, 51, 20),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Dirt),
        positions.create(0, 52, 0),
        positions.create(20, 52, 20),
        FillOperation.Replace
    )
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(10, 55, 10)
    )
    mobs.give(mobs.target(TargetSelectorKind.AllPlayers), Block.TNT, 64)
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
})
```

## Step 9

Go to Minecraft and enter **bomberman** to start a new game!