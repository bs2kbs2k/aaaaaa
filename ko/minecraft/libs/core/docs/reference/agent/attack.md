# 공격하기

Commands the agent to attack in the given direction.

```sig
agent.attack(SixDirection.Forward);
```

## 매개 변수

* **direction**: the direction in which to attack, eg: SixDirection.Forward

## 예시

Makes the agent continuously attack around itself. Useful to defend against monsters!

```blocks
loops.forever(() => {
    agent.attack(SixDirection.Forward);
    agent.attack(SixDirection.Right);
    agent.attack(SixDirection.Back);
    agent.attack(SixDirection.Left);
    loops.pause(1000);
});
```