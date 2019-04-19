# 경작

Commands the agent to till soil in the given direction.

```sig
agent.till(SixDirection.Forward);
```

## 매개 변수

* **direction**: the direction in which to till the soil, eg: SixDirection.Forward

## 예시

Makes the agent till behind itself.

```blocks
agent.till(SixDirection.Back);
```