# 스플리프

Let's build a chat command that creates a *Spleef* arena.

## 단계 1

Find the `||player:on chat command||` block and rename it to **spleef**.

```blocks
player.onChat("spleef", function () {
})
```

## 단계 2

Place a `||blocks:fill||` block in side `||player:on chat command||` to create a layer of lava in the ground between the player position **~0 ~-1 ~0** and ten blocks away north and west **~10 ~-1 ~10**.

The `||blocks:fill||` block takes two locations in the world and fills that area with Lava. By default, it takes coordinates **relative to the player**, that is what the **~** means in slash commands.

* **~0 ~-1 ~0** means 0 blocks west, 1 block down (-1 up), 0 block north.
* **~10 ~-1 ~10** means 10 blocks west, 1 block down (-1 up), 10 block north.

```blocks
player.onChat("spleef", function () {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(10, -1, 10)
    )
})
```

## 단계 3

Put in another `||blocks:fill||` block to create a layer of snow in the air between the player position **~0 ~4 ~0** and ten blocks away north and west **~10 ~4 ~10**.

**~0 ~4 ~0** means 0 blocks west, 4 block up, 0 block north. **~10 ~4 ~10** means 10 blocks west, 4 block up, 10 block north.

```blocks
player.onChat("spleef", function () {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(10, -1, 10)
    )
    blocks.fill(
        blocks.block(Block.Snow),
        positions.create(0, 4, 0),
        positions.create(10, 4, 10)
    )
})
```

## 단계 4

Go to Minecraft, press **t** to open the chat and enter **spleef**.

**GREIFING ALERT!!!** This mod will grief your blocks. Ask your friends before griefing their worlds.

## 단계 5

Add a number parameter to the `||player:on chat command||` block by clicking on the **(+)** sign. This will create a new variable called **num1**. Replace the number **10** with the `||variables:num1||` variable.

So far, the arena created is just 10x10... boring! By using the `||variables:num1||` variable instead, the user can select the size of every game.

```blocks
player.onChat("spleef", function (num1) {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(num1, -1, num1),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Snow),
        positions.create(0, 4, 0),
        positions.create(num1, 4, num1),
        FillOperation.Replace
    )
})
```

## 단계 6

Got to Minecraft and enter `spleef 25` in the chat.

## 단계 7

Place a `||mobs:teleport to position||` block at the end to select all players and teleport them to **~num1/2 ~5 ~num1/2**.

```blocks
player.onChat("spleef", function (num1) {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(num1, -1, num1),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Snow),
        positions.create(0, 4, 0),
        positions.create(num1, 4, num1),
        FillOperation.Replace
    )
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(num1 / 2, 5, num1 / 2)
    )
})
```

## Step 8

Finally, put in a `||gameplay:set game mode||` block to switch **all players** to **survival** mode.

```blocks
player.onChat("spleef", function (num1) {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(num1, -1, num1),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Snow),
        positions.create(0, 4, 0),
        positions.create(num1, 4, num1),
        FillOperation.Replace
    )
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(num1 / 2, 5, num1 / 2)
    )
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
})
```