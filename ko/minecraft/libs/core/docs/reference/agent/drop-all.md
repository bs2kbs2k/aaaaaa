# drop All

Commands the agent to drop its entire inventory in the given direction.

```sig
agent.dropAll(SixDirection.Forward);
```

## 매개 변수

* **direction**: the direction in which to drop items, eg: SixDirection.Forward

## 예시

Makes the agent drop everything it holds below itself.

```blocks
agent.dropAll(SixDirection.Down);
```

## 참고 항목

[drop](/reference/agent/drop)