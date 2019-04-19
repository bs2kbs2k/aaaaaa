# Sand Storm

## Introduction @unplugged

Want to throw some sand around? You will make a small sand storm in this tutorial. You will learn to place a block of sand at a position. Then, you will use `||positions:pick random position||` to make sand appear somewhere at random near you. Finally, a `||loops:repeat||` block is used to make lots of sand show up like a storm!

## Step 1: Chat Command

Rename the `||player:on chat command||` to **"sandstorm"**.

```blocks
player.onChat("sandstorm", function () {
})
```

## Step 2: Add Sand

Place a [`||blocks:place||`](/reference/blocks/place) block inside to create some sand at your position (**~0 ~0 ~0**).

```blocks
player.onChat("sandstorm", function () {
    blocks.place(blocks.block(Block.Sand), positions.create(0, 0, 0))
})
```

## Step 3: Use your slash command!

Go to Minecraft, press **t** to open the chat and enter **sandstorm**. You should see a block at your position.

## Step 4: Random positions

Put a `||positions:pick random position||` block in your `||blocks:place||` block to add some unpredictability.

```blocks
player.onChat("sandstorm", function () {
    blocks.place(blocks.block(Block.Sand), positions.random(
        positions.create(0, 0, 0),
        positions.create(0, 0, 0)
    ))
})
```

## Step 5: From here to there

Edit the positions of the `||positions:pick random position||` block to select a position above the player.

```blocks
player.onChat("sandstorm", function () {
    blocks.place(blocks.block(Block.Sand), positions.random(
        positions.create(-10, 0, -10),
        positions.create(10, 0, 10)
    ))
})
```

## Step 6: Use your slash command!

Go to Minecraft and enter **sandstorm** in the chat. You should see a block of sand fall from the sky.

## Step 7: Repeat

Get a `||loops:repeat||` block and put it around the `||blocks:place||` block to repeat it **100** times.

```blocks
let sandstorm = false
player.onChat("sandstorm", function () {
    for(let i = 0; i < 100; i++) {
        blocks.place(blocks.block(Block.Sand), positions.random(
            positions.create(-10, 0, -10),
            positions.create(10, 0, 10)
        ))
    }
})
```

## Step 8

Go to Minecraft and enter **sandstorm** in the chat. Watch out for sand!