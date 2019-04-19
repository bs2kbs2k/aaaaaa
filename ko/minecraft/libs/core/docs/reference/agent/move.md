# 이동

Request the agent to move in a certain direction.

```sig
agent.move(SixDirection.Forward, 1);
```

## 매개 변수

* **direction**: the direction to move the agent, such as: SixDirection.Forward
* **blocks**: how far the agent should move, in blocks, like: 1

## 예시

Move your agent backwards by 3 blocks.

```blocks
agent.move(SixDirection.Back, 3);
```

## 참고 항목

[`||agent:turn||`](/reference/agent/turn)