# player In Game Mode

Select everyone who's playing in one of the game modes.

```sig
mobs.playersInGameMode(GameMode.Survival);
```

## 매개 변수

* **mode**: the game mode to select all the players from

## 예시

Switch everyone who's playing in`creative` mode to play in `survival` mode.

```blocks
gameplay.setGameMode(
    GameMode.Survival,
    mobs.playersInGameMode(GameMode.Creative)
);
```

## 참고 항목

[`||mobs:set game mode||`](/reference/gameplay/set-game-mode)