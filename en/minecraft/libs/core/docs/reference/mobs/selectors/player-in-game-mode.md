# player In Game Mode

Select everyone who's playing in one of the game modes.

```sig
mobs.playersInGameMode(GameMode.Survival);
```

## Parameters

* **mode**: the game mode to select all the players from

## Example

Switch everyone who's playing in`creative` mode to play in `survival` mode.

```blocks
gameplay.setGameMode(
    GameMode.Survival,
    mobs.playersInGameMode(GameMode.Creative)
);
```

## See also

[`||mobs:set game mode||`](/reference/gameplay/set-game-mode)