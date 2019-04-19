# place

Places an item or block in the world from the agent's currently selected inventory slot.

```sig
agent.place(SixDirection.Back);
```

## 매개 변수

* **direction**: the direction in which to place the item, eg: SixDirection.Back

## 예시

Places a block above the agent. This will only work if your agent has at least one block in its currently selected inventory slot.

```blocks
agent.place(SixDirection.Up);
```

## 참고 항목

[set-slot](/reference/agent/set-slot)