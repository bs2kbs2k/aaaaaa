# Lava Tower

## Introduction @unplugged

Hey, let's try something dramatic! This tutorial makes a lava tower.

It slowly descends from the sky, and then our command waits for it to flow to the ground. You can then add some water to cool the lava. You're going to use a `||loops:pause||` block to add some wait time and let the lava reach the ground before cooling it down.

![The sky is falling](/static/tutorials/lava-tower.gif)

## Step 1: Chat Command

Place an `||player:on chat command||` block to define a new chat command called **"tower"**.

```blocks
player.onChat("tower", function () {
})
```

## Step 2: Lava from above

Using `||blocks:place||`, put a lava block in the sky **20** blocks above you.

```blocks
player.onChat("tower", function () {
    blocks.place(blocks.block(Block.Lava), positions.create(5, 20, 0))
})
```

## Step 3: Just add water

Use another `||blocks:place||` to add some water to cool the flowing lava. Put it **135** blocks above.

We want to make sure the lava has time to flow all the way to the ground before the water reaches it, so make the water appear very high in the sky, **135** blocks above you.

```blocks
player.onChat("tower", function () {
    blocks.place(blocks.block(Block.Lava), positions.create(5, 20, 0))
    blocks.place(blocks.block(Block.Water), positions.create(5, 135, 0))
})
```

## Step 4: Stop the water

Ok, get rid of the water. Use a `||loops:pause||` of **625** milliseconds. Add a `||blocks:place||` with **air** to dry the water.

```blocks
player.onChat("tower", function () {
    blocks.place(blocks.block(Block.Lava), positions.create(5, 20, 0))
    blocks.place(blocks.block(Block.Water), positions.create(5, 135, 0))
    loops.pause(625)
    blocks.place(blocks.block(Block.Air), positions.create(5, 135, 0))
})
```

## Step 6: Try it out!

Go to Minecraft, type **t** to open the chat and enter **tower**. It will take some time for the lava to cool and for the water to dry. **Be careful, lava can be destructive!**