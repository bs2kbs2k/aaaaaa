# to World

Make a new ***world*** position from another position. If the other position is a ***relative*** position, it is converted to a new ***world*** position.

```sig
positions.create(0, 0, 0).toWorld();
```

Read about how positions work in the [positions](/reference/positions) reference.

## 예시

Convert the relative position above the player's head to a world position. Then, display the position in the chat.

```blocks
player.say("The block above my head is at position: " + positions.create(0, 2, 0).toWorld())
```