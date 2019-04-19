# get Item Count

Gets the number of items in the specified slot.

```sig
agent.getItemCount(1);
```

## Parameters

* **slot**: the slot index for which to count items, from 1 to 27, eg: 1

## Example

Displays how many blocks the agent has in its second slot in the game chat.

```blocks
player.say("" + agent.getItemCount(2));
```

## See Also

[get-item-space](/reference/agent/get-item-space)