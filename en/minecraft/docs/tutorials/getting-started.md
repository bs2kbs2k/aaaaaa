# Getting started

## Chickens! @fullscreen

Let's get started with coding in Minecraft! Why not add some life to your world? Maybe a chicken... No, let's have **LOTS OF CHICKENS**!!!

![Chicken rain](/static/getting-started/chickenrain.gif)

## Step 1: Chat Commands

Rename the `||player:on chat command||` name to **chicken**.

You see the `||player:on chat command||`? It's named **"run"**. Go click on that name and change it to **"chicken"**.

```block
player.onChat("chicken", function () {
})
```

## Step 2

Place a `||mobs:spawn||` block to spawn a chicken at your position.

The blocks under `||player:on chat command||` will run when you type **chicken** in the Minecraft chat. **~0 ~0 ~0** is the relative 3D position of the player.

```block
player.onChat("chicken", function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
})
```

## Step 3

Change the spawn position to 10 blocks above your head.

The second number in **~0 ~10 ~0** means **10** blocks **up** of the player altitude. The **~** symbol means that the number is relative to the player.

```block
player.onChat("chicken", function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
})
```

## Step 4

Go to Minecraft, press **t** to open the chat and enter **chicken**. You should see a flying chicken!

## Step 5

The chicken is lonely. Place a `||loops:repeat||` block around `||mobs:spawn||` to create **100** chickens!

```block
player.onChat("chicken", function () {
    for (let i = 0; i < 100; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

## Step 6

Well Done! You've completed your first Mod!