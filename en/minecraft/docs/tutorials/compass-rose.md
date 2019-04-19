# Compass Rose

## Introduction @unplugged

This tutorial shows you how to create words and letters (text) from blocks. The text is placed in the Minecraft world at a position you choose using the `||blocks:print||` code block. The object you will make is called a compass rose. This is a 2D marker showing the *North*, *South*, *East*, and *West* directions. In the last step, you will add another dimension to the compass rose to show the *Up* and *Down* directions.

## Step 1

Place an `||player:on chat command||` block and rename it to **compassrose**.

```blocks
player.onChat("compassrose", function () {
})
```

## Step 2

Place a `||blocks:print||` block in your chat command. Change **"HELLO"** to **"E"**.

```blocks
player.onChat("compassrose", function () {
    blocks.print(
    "E",
    blocks.block(Block.Glowstone),
    positions.create(0, 0, 0),
    CompassDirection.West
    )
})
```

## Step 3

Go to Minecraft, press **t** to open the chat and enter **compassrose**.

The `||blocks:print||` block will place a big **"E"** in the Minecraft world at your current position.

## Step 4

Change the position to **~20 ~0 ~0** so that `||blocks:print||` places the **"E"** letter **20** blocks East of your current position.

The 1st number, **x** of a position represents the East/West location. A positive value goes East, negative goes west.

The **~** symbol means that the position is relative to the player position rather than to the world. Thus, **~20 ~0 ~0** means **20 blocks East** of the player position.

```blocks
player.onChat("compassrose", function () {
    blocks.print(
        "E",
        blocks.block(Block.Glowstone),
        positions.create(20, 0, 0),
        CompassDirection.West
    )
})
```

## Step 5

Go to Minecraft and enter **compassrose** in the chat.

The **"E"** letter is now printed 20 blocks away.

## Step 6

Place another `||blocks:print||` block to show **"W"** 20 blocks West. Try it in Minecraft.

West goes negative so the position is **~-20 ~0 ~0**. Don't move until all letters are printed!.

```blocks
player.onChat("compassrose", function () {
    blocks.print(
        "E",
        blocks.block(Block.Glowstone),
        positions.create(20, 0, 0),
        CompassDirection.West
    )
    blocks.print(
        "W",
        blocks.block(Block.Glowstone),
        positions.create(-20, 0, 0),
        CompassDirection.West
    )
})
```

## Step 7

Place more `||blocks:print||` blocks to show **"N"** 20 blocks North, **"S"** 20 blocks South. Try it in Minecraft.

The 3rd number, **z**, of the is the South/North coordinate. A positive value goes South, a **negative** value goes North.

```blocks
    blocks.print(
        "N",
        blocks.block(Block.Glowstone),
        positions.create(0, 0, -20),
        CompassDirection.West
    )
    blocks.print(
        "S",
        blocks.block(Block.Glowstone),
        positions.create(0, 0, 20),
        CompassDirection.West
    )
```

## Step 8

Place more `||blocks:print||` blocks to show **"U"** 20 blocks Up, **"D"** 20 blocks Down. Try it in Minecraft.

The 2nd number, **y**, of the position is the Up/Down elevation. A positive value goes Up, a negative value goes Down.

```blocks
    blocks.print(
        "U",
        blocks.block(Block.Glowstone),
        positions.create(0, 20, 0),
        CompassDirection.West
    )
    blocks.print(
        "D",
        blocks.block(Block.Glowstone),
        positions.create(0, -20, 0),
        CompassDirection.West
    )
```