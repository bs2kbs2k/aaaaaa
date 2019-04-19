# Super Digger

## Introduction @unplugged

Let's build a command that gives you **super digging powers**!

![Super digging!](/static/tutorials/super-digger.gif)

## Step 1: Chat Command

Replace **"run"** with **"dig"** in the `||player:on chat command||` block.

```blocks
player.onChat("dig", function () {
})
```

## Step 2: Mine a little

Use the `||blocks:fill||` block to fill your current location with `air` when the chat command is entered.

```blocks
player.onChat("dig", function () {
        blocks.fill(blocks.block(Block.Air), positions.create(0, 0, 0), positions.create(0, 0, 0))
})
```

## Step 3: Mine a lot

We don't want to mine just one block at a time, so let's edit the `"to"` position in the `||blocks:fill||` block to mine a `5x5x5` cube. Digging it big time!

```blocks
player.onChat("dig", function () {
    blocks.fill(blocks.block(Block.Air), positions.create(0, 0, 0), positions.create(5, 5, 5))
})
```

## Step 4:

Go to Minecraft, press **t** to open the chat and enter **dig**. Try moving **into** things!

**GRIEFING ALERT! This mod can mess up your world!**

## Step 5: Keep digging and digging

Place a `||loops:while||` block around the `||blocks:fill||` block to repeat it forever.

```blocks
player.onChat("dig", function () {
    while (true) {
        blocks.fill(
            blocks.block(Block.Air),
            positions.create(-5, 0, -5),
            positions.create(5, 5, 5),
            FillOperation.Replace
        )
    }
})
```

## Step 6

Go to Minecraft and enter **dig** in the chat. **GRIEFING ALERT! This mod can mess up your world!**

## Step 7: Dig under your feet

Edit the position in `||blocks:fill||` to dig under the player's feet.

```blocks
player.onChat("dig", function () {
    while (true) {
        blocks.fill(
            blocks.block(Block.Air),
            positions.create(-5, -5, -5),
            positions.create(5, 5, 5),
            FillOperation.Replace
        )
    }
})
```

## Step 8

Go to Minecraft, put your player in **flying mode** and enter **dig** in the chat. **GRIEFING ALERT! This mod can mess up your world!**