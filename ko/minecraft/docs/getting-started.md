# 튜토리얼 따라해보기

## 닭들! @fullscreen

Let's get started with coding in Minecraft! Why not add some life to your world? Maybe a chicken... No, let's have **LOTS OF CHICKENS**!!!

![하늘에서 닭들이 내린다면](/static/getting-started/chickenrain.gif)

## Step 1: Chat Commands

Rename the `||player:on chat command||` name to **chicken**.

Click on **"run"** and change it to **"chicken"**.

```blocks
player.onChat("chicken", function () {
})
```

## 단계 2

Place a `||mobs:spawn||` block to spawn a chicken at your position.

The blocks under `||player:on chat command||` will run when you type **chicken** in the Minecraft chat. **~0 ~0 ~0** is the relative 3D position of the player.

```blocks
player.onChat("chicken", function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
})
```

## 단계 3

Change the spawn position to 10 blocks above your head.

The second number in **~0 ~10 ~0** means **10** blocks **up** of the player altitude. The **~** symbol means that the number is relative to the player.

```blocks
player.onChat("chicken", function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
})
```

## 단계 4

Go to Minecraft, press **t** to open the chat and enter **chicken**. You should see a flying chicken!

## 단계 5

The chicken is lonely. Place a `||loops:repeat||` block around `||mobs:spawn||` to create **100** chickens!

```blocks
player.onChat("chicken", function () {
    for (let i = 0; i < 100; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

## 단계 6

Well Done! You've completed your first Mod!