# Leaping Salmon

## Introduction @unplugged

Look out, salmon are leaping dangerously high! We must create ponds for them to land in!

## Step 1

We'll use a **Trident** to cause salmon to make giant leaps into the sky. Add a `||player:on item used||` block to your code and set the item type to **Trident**.

```blocks
player.onItemInteracted(Item.Trident, function () {

})
```

## Step 2

We want multiple fish to spawn for each Trident use, so drag a `||loops:repeat||` block to the `||player:on item used||` block and set the repeat number to **6**.

```blocks
player.onItemInteracted(Item.Trident, function () {
    for (let i = 0; i < 6; i++) {
    }
})
```

## Step 3

Now it's time to spawn the salmon. Drag a `||mobs:spawn||` block into the `||loops:repeat||` block and set the animal type to **Salmon**.

```blocks
player.onItemInteracted(Item.Trident, function () {
    for (let i = 0; i < 6; i++) {
        mobs.spawn(AnimalMob.Salmon, positions.create(0, 0, 0))
    }
})
```

## Step 4

We'll make it so the salmon spawn into a random location to make it harder to catch them. Drag a `||positions: pick random position||` into the `||mobs:spawn||` block. Set the **from** position to **~-6 ~60 ~-6** and the **to** position to **~6 ~60 ~6**. That'll make them spawn high in the sky!

```blocks
player.onItemInteracted(Item.Trident, function () {
    for (let i = 0; i < 6; i++) {
        mobs.spawn(AnimalMob.Salmon, positions.random(
                positions.create(-6, 60, -6),
                positions.create(6, 60, 6)
            ))
    }
})
```

## Step 5

We've just made it so the salmon leap extremely high! We should create a pond to catch them so the don't get injured when they land. Add a second `||player:on item used||` to your code, and set the item to **Kelp**.

```blocks
player.onItemInteracted(blocks.item(Item.Trident), function () {
    for (let i = 0; i < 6; i++) {
        mobs.spawn(AnimalMob.Salmon, positions.random(
            positions.create(-6, 60, -6),
            positions.create(6, 60, 6)
        ))
    }
})
player.onItemInteracted(blocks.item(Item.Kelp), function () {

})
```

## Step 6

Drag a `||blocks:fill||` block and put it into the `||player:on item used||` block set to **Kelp**. The falling fish need to land in water, so set the fill block type to **Water**.

```blocks
player.onItemInteracted(blocks.item(Item.Trident), function () {
    for (let i = 0; i < 6; i++) {
        mobs.spawn(AnimalMob.Salmon, positions.random(
            positions.create(-6, 60, -6),
            positions.create(6, 60, 6)
        ))
    }
})
player.onItemInteracted(blocks.item(Item.Kelp), function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(0, 0, 0),
        positions.create(0, 0, 0),
        FillOperation.Replace
    )
})
```

## Step 7

Finally, we must change the size of our pond so the fish can land right into it. In the `||blocks:fill||` block, set the **from** position to **~-2 ~-1 ~-2** and the **to** position to **~2 ~-1 ~2**. This creates a 5 x 5 shallow pool of water around the player.

```blocks
player.onItemInteracted(blocks.item(Item.Trident), function () {
    for (let i = 0; i < 6; i++) {
        mobs.spawn(AnimalMob.Salmon, positions.random(
            positions.create(-6, 60, -6),
            positions.create(6, 60, 6)
        ))
    }
})
player.onItemInteracted(blocks.item(Item.Kelp), function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-2, -1, -2),
        positions.create(2, -1, 2),
        FillOperation.Replace
    )
})
```

## Step 8

You're all done! Go in-game and add a **Trident** and some **Kelp** to your equipment. Use the Trident to make salmon leap high in the sky. Then, quickly equip the Kelp and use it to create a pond underneath the fish so they can land safely. You'll have to react quickly!