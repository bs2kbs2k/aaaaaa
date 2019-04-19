# Gold stairs

## Introduction @unplugged

Climb higher and go for the gold! You will build some stairs out of gold blocks in this tutorial. The builder tool will do the work by placing gold blocks where you tell it to. You will build a golden stairway to the sky.

![Stairs made of solid gold](/static/tutorials/gold-stairs.gif)

## Step 1

Place a `||player:on chat command||` block and rename it to **goldstairs**.

```blocks
player.onChat("goldstairs", function () {
})
```

## Step 2

Place a `||builder:builder teleport to||` block into the chat command to teleport the player to your position.

The **builder** is similar to the agent but invisible.

```blocks
player.onChat("goldstairs", function () {
    builder.teleportTo(positions.create(0, 0, 0))
})
```

## Step 3

Put two `||builder:builder move||` blocks in the `||loops:repeat||` to move forward and up.

To build a single stair, we tell the builder to move forward, then up, then forward, then up...

```blocks
player.onChat("goldstairs", function () {
    builder.teleportTo(positions.create(0, 0, 0))
    builder.move(SixDirection.Forward, 1)
    builder.move(SixDirection.Up, 1)
})
```

## Step 4

Add a `||builder:builder trace path||` to tell the builder to fill the path with **gold blocks**.

```blocks
player.onChat("goldstairs", function () {
    builder.teleportTo(positions.create(0, 0, 0))
    builder.move(SixDirection.Forward, 1)
    builder.move(SixDirection.Up, 1)
    builder.tracePath(blocks.block(Block.GoldBlock))
})
```

## Step 5

Go to Minecraft, type **t** to open the chat and enter **goldstairs**. You should see 2 new gold blocks appear.

## Step 6

Now, get a `||loops:repeat||` block with `25` times and put it around the `||builder:builder move||` blocks to build **25** stairs.

```blocks
player.onChat("goldstairs", function () {
    builder.teleportTo(positions.create(0, 0, 0))
    for (let i = 0; i < 25; i++) {
        builder.move(SixDirection.Forward, 1)
        builder.move(SixDirection.Up, 1)
    }
    builder.tracePath(blocks.block(Block.GoldBlock))
})
```

## Step 7

Go to Minecraft and enter **goldstairs** in the chat. You should see a long gold block staircase get created.

## Step 8

Get a `||mobs:teleport to position||` block to teleport all players to the base of the stairs.

```blocks
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(0, 0, 0)
    )
```

## Step 9

Place a `||gameplay:set game mode||` block to switch all players to `creative` mode.

```blocks
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
```

## Step 10

Go to Minecraft and enter **goldstairs** in the chat. The first player to the top wins!

```package
builder
```