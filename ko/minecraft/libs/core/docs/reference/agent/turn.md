# turn

Turn the agent in a specific direction.

```sig
agent.turn(TurnDirection.Left);
```

## 매개 변수

* **direction**: the turn direction, like: TurnDirection.Left

## 예시

Make your agent turn around by making it turn right twice.

```blocks
for (let i = 0; i < 2; i++) {
    agent.turn(TurnDirection.Right);
}
```

## 참고 항목

[`||agent:move||`](/reference/agent/move)