# repeater

Create a repeater signal block. You choose the direction it faces and the signal delay time. The delay time is a number of game ticks.

```sig
blocks.repeater(CompassDirection.West, 1);
```

## Parameters

* **direction**: the direction in which the repeater is facing
* **delay**: the delay time for the repeater, in game ticks

The [Minecraft wiki](http://minecraft.gamepedia.com/Redstone_Repeater#Data_values) has more information about the values for repeater direction and delay time.

## Example

Place a repeater near the player facing North. Give it a tick delay of `3`.

```blocks
blocks.place(blocks.repeater(CompassDirection.North, 3), positions.create(1, 0, 0));
```

## See also

[`||blocks:comparator||`](/reference/blocks/comparator)