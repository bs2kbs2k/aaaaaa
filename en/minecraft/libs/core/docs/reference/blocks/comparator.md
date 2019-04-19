# comparator

Create a comparator facing in the direction you choose. You can decide what type of comparison you want it to make.

```sig
blocks.comparator(CompassDirection.West, ComparatorMode.Compare);
```

## Parameters

* **direction**: the direction which the comparator is facing
* **mode**: the comparison mode of the comparator: > * `compare`: compares surrounding block signal strength > * `subtract`: subtract the signal strength of one surrounding block from the signal strength of the other

Read about comparator states in the [Minecraft wiki](http://minecraft.gamepedia.com/Redstone_Comparator#Data_values).

## Example

Place a comparator facing North and in substraction mode near the player.

```blocks
blocks.place(blocks.comparator(CompassDirection.North, ComparatorMode.Substract), positions.create(1, 0, 0));
```

## See also

[`||blocks:repeater||`](/reference/blocks/repeater)