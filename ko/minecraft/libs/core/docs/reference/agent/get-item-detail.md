# get Item Detail

Gets the ID of the item in the specified inventory slot of the agent.

```sig
agent.getItemDetail(1);
```

## 매개 변수

* **slot**: the slot index for which to return the item info, from 1 to 27, eg: 1

## 예시

Displays the item ID from the agent's second slot in the game chat.

```blocks
player.say("" + agent.getItemDetail(2));
```