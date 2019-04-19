# place

Places an item or block in the world from the agent's currently selected inventory slot.

```sig
agent.place(SixDirection.Back);
```

## Parameters

* **direction**: the direction in which to place the item, eg: SixDirection.Back

## Example

Places a block above the agent. This will only work if your agent has at least one block in its currently selected inventory slot.

```blocks
agent.place(SixDirection.Up);
```

## See Also

[set-slot](/reference/agent/set-slot)