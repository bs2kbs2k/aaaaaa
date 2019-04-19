# collect All

Commands the agent to collect all nearby blocks and items.

```sig
agent.collectAll();
```

## Example

Makes the agent follow the player and collect any nearby block or item.

```blocks
loops.forever(() => {
    agent.teleportToPlayer();
    agent.collectAll();
});
```

## See Also

[collect](/reference/agent/collect)