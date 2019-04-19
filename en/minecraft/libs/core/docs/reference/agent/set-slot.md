# set Slot

Sets the agent's active inventory slot.

Slots are counted from left to right and then top to bottom, starting at the top-left corner of the agent's inventory. This means that the first row at the top of the agent's inventory has slots 1 through 9. The second row has slots 10 through 18, and the bottom row has slots 19 through 27.

```sig
agent.setSlot(1);
```

## Parameters

* **slot**: the slot index between 1 and 27, such as: 1 > The slots are found in the rows like this:

> 01 - 02 - 03 - 04 - 05 - 06 - 07 - 08 - 09
> 
> 10 - 11 - 12 - 13 - 14 - 15 - 16 - 17 - 18
> 
> 19 - 20 - 21 - 22 - 23 - 24 - 25 - 26 - 27

## Example

Select the second slot in the agent's inventory, and then make the agent place what it holds in that slot.

```blocks
agent.setSlot(2);
agent.place(SixDirection.Forward);
```