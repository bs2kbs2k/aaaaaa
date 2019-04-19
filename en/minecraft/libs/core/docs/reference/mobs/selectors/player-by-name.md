# player By Name

Select a player using their name.

```sig
mobs.playerByName("");
```

## Parameters

* **name**: the name of the player to select

## Example

Gives diamond to the current player using their player name.

```blocks
mobs.give(
    mobs.playerByName(player.name()),
    blocks.item(Item.Diamond),
    1
);
```

## See also

[`||player:name||`](/reference/player/name)