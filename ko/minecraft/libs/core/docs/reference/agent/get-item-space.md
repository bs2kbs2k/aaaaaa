# get Item Space

Gets the remaining space in the specified slot.

```sig
agent.getItemSpace(1);
```

## 매개 변수

* **slot**: the slot index for which to count the remaining space, from 1 to 27, eg: 1

## 예시

Displays how much space is left in the agent's second slot in the game chat.

```blocks
player.say("" + agent.getItemSpace(2));
```

## 참고 항목

[get-item-count](/reference/agent/get-item-count)