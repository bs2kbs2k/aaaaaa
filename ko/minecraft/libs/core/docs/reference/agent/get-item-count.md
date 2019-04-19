# get Item Count

Gets the number of items in the specified slot.

```sig
agent.getItemCount(1);
```

## 매개 변수

* **slot**: the slot index for which to count items, from 1 to 27, eg: 1

## 예시

Displays how many blocks the agent has in its second slot in the game chat.

```blocks
player.say("" + agent.getItemCount(2));
```

## 참고 항목

[get-item-space](/reference/agent/get-item-space)