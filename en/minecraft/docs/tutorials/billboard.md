# Billboard

## Introduction @unplugged

Want to use big words? Make a billboard!

![A billboard](/static/tutorials/billboard.gif)

## Step 1: Chat Command

Rename **"run"** to **"print"** in the `||player:on chat command||` block.

```blocks
player.onChat("print", function () {
})
```

## Step 2: Printing some text

Place a `||blocks:print||` block inside `||player:on chat command||` and use your name as the text.

```blocks
player.onChat("print", function () {
    blocks.print(
        "Alex",
        blocks.block(Block.TNT),
        positions.create(0, 0, 0),
        CompassDirection.West
    )
})
```

## Step 3: Use your slash command!

Go to Minecraft, press **t** to open the chat and enter **print** to see your name appear!