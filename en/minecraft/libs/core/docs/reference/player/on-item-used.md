# on Item Used

Runs code when you interact with, or use, an item in the game.

```sig
player.onItemInteracted(Item.IronShovel, function () {
})
```

When using the keyboard and mouse, an item is used if you right-click with the mouse while having the item equipped. For touch, an item is used when you press on the screen and hold.

### Parameters

* **item**: the type of item used that will cause the code to run, such as: `Item.Trident`
* **handler**: the code to run when the item is used by the current player

### Example

The following code makes lightning strike near the player when they use a Diamond Sword. Unlimited power!

```blocks
player.onItemInteracted(Item.DiamondSword, function () {
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(10, 0, 0))
})
```