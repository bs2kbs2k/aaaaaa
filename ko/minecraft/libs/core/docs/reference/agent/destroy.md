# 파괴하기

Commands the agent to destroy a block in the given direction.

```sig
agent.destroy(SixDirection.Forward);
```

## 매개 변수

* **direction**: the direction in which the agent will destroy a block, eg: SixDirection.Forward

## 예시

If there's a block in front of the agent, the agent will destroy it.

```blocks
if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
    agent.destroy(SixDirection.Forward);
}
```