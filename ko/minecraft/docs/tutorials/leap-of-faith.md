# 신뢰의 도약

Let's build a *Leap of Faith* mini-game.

### 단계 1

Place a `||player:on chat command||` to define a new chat command and name it **"lof"**.

```blocks
player.onChat("lof", function () {
})
```

### 단계 2

Put in a `||blocks:fill||` block to fill a `3x3x3` pool of water in the ground.

```blocks
player.onChat("lof", function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-1, -3, -1),
        positions.create(1, -1, 1)
    )
})
```

### 단계 3

Go to Minecraft, press **t** to open the chat and enter **lof**. Make sure a pool is created.

### 단계 4

Add another `||blocks:fill||` block to build a `3x3` stone platform at **128** blocks high.

```blocks
player.onChat("lof", function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-1, -3, -1),
        positions.create(1, -1, 1)
    )
    blocks.fill(
        blocks.block(Block.Stone),
        positions.create(-1, 128, -1),
        positions.create(1, 128, 1)
    )
})
```

### 단계 5

Go to Minecraft and enter **lof** in the chat. Make sure a pool and a platform is created.

### 단계 6

Add a `||player:teleport to||` block at the end of the command to teleport the player above the platform.

```blocks
player.onChat("lof", function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-1, -3, -1),
        positions.create(1, -1, 1)
    )
    blocks.fill(
        blocks.block(Block.Stone),
        positions.create(-1, 128, -1),
        positions.create(1, 128, 1)
    )
    player.teleport(positions.create(0, 130, 0))
})
```

### 단계 7

Place a `||gameplay:set game mode||` block after the `||player:teleport to||` to turn on `survival` mode for the player.

```blocks
player.onChat("lof", function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-1, -3, -1),
        positions.create(1, -1, 1)
    )
    blocks.fill(
        blocks.block(Block.Stone),
        positions.create(-1, 128, -1),
        positions.create(1, 128, 1)
    )
    player.teleport(positions.create(0, 130, 0))
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.NearestPlayer)
    )
})
```

### Step 8

Go to Minecraft and enter **lof** to play your game!