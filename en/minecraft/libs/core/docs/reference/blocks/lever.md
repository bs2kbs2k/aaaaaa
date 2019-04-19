# lever

Create a lever. The lever points in the direction you set.

```sig
blocks.lever(LeverPosition.BlockBottomEastWhenOff);
```

## Parameters

* **position**: the position of the lever

You can read about the lever positions you can use in [Minecraft wiki](http://minecraft.gamepedia.com/Lever#Data_values).

## Example

Place a stone block near the player. Attach an upside-down lever to the stone that points South.

```blocks
blocks.place(blocks.block(Block.Stone), positions.create(1, 2, 0));
blocks.place(blocks.lever(LeverPosition.BlockBottomPointsSouthWhenOff), positions.create(1, 1, 0));
```