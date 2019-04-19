# drop

Drops an item from the inventory.

```sig
agent.drop(
    SixDirection.Back,
    1,
    1
);
```

## 매개 변수

* **slot**: the slot from which the item will be dropped, from 1 to 27, eg: 1
* **direction**: the direction in which to drop the item, eg: SixDirection.Back
* **quantity**: the quantity of items to drop, eg: 1

## 예시

Causes the agent to drop 15 blocks from its fifth inventory slot behind itself. If the agent does not have anything in the fifth inventory slot, then nothing will be dropped.

```blocks
agent.drop(
    SixDirection.Back,
    5,
    15
);
```

## 참고 항목

[drop-all](/reference/agent/drop-all)