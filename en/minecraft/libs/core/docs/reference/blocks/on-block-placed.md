# on Block Placed

Run code when a certain type of block is placed.

```sig
blocks.onBlockPlaced(blocks.block(Block.Grass), () => {

});
```

## Parameters

* **block**: the type of block that, when it is placed, will start some code
* **handler**: this is the code to run when the type of block selected in **block** is placed in the world

## Example

This code displays a comment in the game chat when a block of gold is placed in the world.

```blocks
blocks.onBlockPlaced(blocks.block(Block.GoldBlock), () => {
    player.say("Shiny!");
});
```

## See Also

[`||blocks:on block broken||`](/reference/blocks/on-block-broken)