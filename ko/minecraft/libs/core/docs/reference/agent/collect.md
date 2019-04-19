# collect

Commands the agent to Collect a block or item of the specified type.

```sig
agent.collect(blocks.item(Item.IronShovel));
```

## 매개 변수

* **block**: the type of the block or item to collect

## 예시

Makes the agent collect any nearby diamonds.

```blocks
agent.collect(blocks.item(Item.Diamond));
```

## 참고 항목

[collect-all](/reference/agent/collect-all)