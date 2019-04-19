# collect All

Commands the agent to collect all nearby blocks and items.

```sig
agent.collectAll();
```

## 예시

Makes the agent follow the player and collect any nearby block or item.

```blocks
loops.forever(() => {
    agent.teleportToPlayer();
    agent.collectAll();
});
```

## 참고 항목

[collect](/reference/agent/collect)