# transfer

Transfer items from an inventory slot to another slot.

The agent's inventory slots are numbered in a certain way. See how the slots are arranged in [`||agent:set slot||`](/reference/agent/set-slot).

```sig
agent.transfer(
    1,
    1,
    2
);
```

## Parameters

* **quantity**: the quantity of items to transfer, such as: 1
* **sourceSlot**: the source slot index, from 1 to 27, like: 1
* **destinationSlot**: the inventory slot in which to drop the items, from 1 to 27, for example: 2

## Example

Transfer 5 blocks from the agent's fifth inventory slot to its first slot (slot 5 to slot 1).

```blocks
agent.transfer(
    5,
    5,
    1
);
```

## See Also

[`||agent:set slot||`](/reference/agent/set-slot)