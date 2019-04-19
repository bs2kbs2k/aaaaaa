# Mega Jump

## Introduction @unplugged

Build a mod that lets you jump high... **as high as you want!**

![A mega jump](/static/tutorials/mega-jump.gif)

## Step 1: Chat Command

Rename **"run"** to **"jump"** in the `||player:on chat command||` block.

```blocks
player.onChat("jump", function() {
})
```

## Step 2: Teleport the player

Place a `||player:teleport||` block inside `||player:on chat command||` to teleport the player `100` blocks higher.

```blocks
player.onChat("jump", function() {
    player.teleport(positions.create(0, 100, 0))
})
```

## Step 3: Use your slash command!

Go to Minecraft, type **t** to open the chat and enter **jump**.

## Step 4: Add a parameter to the slash command

Click the "+" sign on the `||player:on chat command||` block to add a **number** parameter to the command.

```blocks
player.onChat("jump", function (num1) {
    player.teleport(positions.create(0, 100, 0))
})
```

## Step 5: Jump the amount entered by the user.

Use the `||variables:num1||` variable instead of `100` in the code so you will jump by the amount entered by the player.

```blocks
player.onChat("jump", function (num1) {
    player.teleport(positions.create(0, num1, 0))
})
```

## Step 6: Use your slash command!

Go to Minecraft and enter **jump 50** in the chat. You should jump by 50 blocks instead of 100. Try **jump 1000**...