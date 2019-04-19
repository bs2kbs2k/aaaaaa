# player By Name

Select a player using their name.

```sig
mobs.playerByName("");
```

## 매개 변수

* **name**: the name of the player to select

## 예시

Gives diamond to the current player using their player name.

```blocks
mobs.give(
    mobs.playerByName(player.name()),
    blocks.item(Item.Diamond),
    1
);
```

## 참고 항목

[`||player:name||`](/reference/player/name)