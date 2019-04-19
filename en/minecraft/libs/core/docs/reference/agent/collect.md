# collect

Commands the agent to Collect a block or item of the specified type.

```sig
agent.collect(blocks.item(Item.IronShovel));
```

## Parameters

* **block**: the type of the block or item to collect

## Example

Makes the agent collect any nearby diamonds.

```blocks
agent.collect(blocks.item(Item.Diamond));
```

## See Also

[collect-all](/reference/agent/collect-all)