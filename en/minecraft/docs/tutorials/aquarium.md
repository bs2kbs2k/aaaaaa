# Aquarium

## Introduction @unplugged

Let's build a nice, cozy aquarium for our marine friends!

## Step 1

We'll make it so our aquarium is built when we swing a **Trident**! Add a `||player:on item used||` block to your code and set the item type to **Trident**.

```blocks
player.onItemInteracted(Item.Trident, function () {

})
```

## Step 2

Add a `||blocks:fill||` block to your code to build the glass structure.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(0, 0, 0),
        positions.create(0, 0, 0),
        FillOperation.Replace
    )
})
```

## Step 3

A size of 8 x 8 x 20 should hold enough specimens. Change the **from** position to **~5 ~0 ~-10** and the **to** position to **~12 ~7 ~10** in your `||blocks:fill||`. We use 5 and 12 as the first coordinates, otherwise we'll end up swimming with the fish!

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
})
```

## Step 4

Next, we'll use a `||blocks:fill||` block for the water. Add one to your code and set the block type to **Water**. We only want to fill the **inside** of the aquarium, so set the **from** position to **~6 ~0 ~-9** and the **to** position to **~11 ~6 ~9**.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
})
```

## Step 5

The aquarium is ready to be populated! We'll want multiple fish and coral living inside it, so we'll need a `||loops:repeat||` block to create them all. Add one to your code.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
    for (let i = 0; i < 4; i++) {
    }
})
```

## Step 6

Let's start with the fish. Drag a `||mobs:spawn||` block inside the `||loops:repeat||` block, and change the animal type to your favorite fish.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
    for (let i = 0; i < 4; i++) {
        mobs.spawn(AnimalMob.Dolphin, positions.create(0, 0, 0))
    }
})
```

## Step 7

We'll now make the fish spawn randomly inside the aquarium. Drag a `||positions:pick random position||` inside the `||mobs:spawn||` block, and change the **from** and **to** positions to the same area as the water: **~6 ~0 ~-9** and **~11 ~6 ~9**.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
    for (let i = 0; i < 4; i++) {
        mobs.spawn(AnimalMob.Dolphin, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
    }
})
```

## Step 8

Time to decorate! Drag a `||blocks:place||` block inside the `||loops:repeat||` block and set the block type to your favorite coral. Drag a `||positions:pick random position||` block inside it, and change the positions to **~6 ~0 ~-9** and **~11 ~0 ~9** so the coral spawns on the floor.

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
    for (let i = 0; i < 4; i++) {
        mobs.spawn(AnimalMob.Dolphin, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        blocks.place(Block.BubbleCoralFan, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
    }
})
```

## Step 9

Bring your aquarium to life by adding more fish and coral in the `||loops:repeat||` block! To speed up the process, right-click on a `||blocks:place||` or `||mobs:spawn||` block and select **Duplicate**. When you're done, go in-game and use a trident to see your aquarium take shape!

```blocks
player.onItemInteracted(Item.Trident, function () {
    blocks.fill(
        Block.GlassPane,
        positions.create(5, 0, -10),
        positions.create(12, 7, 10),
        FillOperation.Replace
    )
    blocks.fill(
        Block.Water,
        positions.create(6, 0, -9),
        positions.create(11, 6, 9),
        FillOperation.Replace
    )
    for (let i = 0; i < 4; i++) {
        mobs.spawn(AnimalMob.Dolphin, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        mobs.spawn(AnimalMob.Pufferfish, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        mobs.spawn(AnimalMob.Salmon, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        mobs.spawn(AnimalMob.TropicalFish, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        mobs.spawn(AnimalMob.Cod, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 6, 9)
        ))
        blocks.place(Block.BubbleCoralFan, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
        blocks.place(Block.Seagrass, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
        blocks.place(Block.Kelp, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
        blocks.place(Block.HornCoral, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
        blocks.place(Block.TubeCoral, positions.random(
            positions.create(6, 0, -9),
            positions.create(11, 0, 9)
        ))
    }
})
```