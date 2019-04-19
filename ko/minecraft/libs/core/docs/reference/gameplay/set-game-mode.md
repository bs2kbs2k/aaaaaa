# set Game Mode

Change the game mode for the players you choose.

```sig
gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## 매개 변수

* **mode**: the new game mode, like: *GameMode.Survival*, > * `survival`: This is the default Minecraft playing mode. 플레이어들은 자신이 만들고 싶은 재료들이나 장소들을 모아야 합니다. The player's health, hunger, experience and oxygen are enabled. Tools and equipment durability is enabled. In this mode, the player can die and will return to the spawn point if they do. > * `creative`: Players can get an unlimited amount of blocks or items in the game. Players can fly around in the world and destroy blocks instantly. This mode is meant for players that want to spend time building things. > * `adventure`: Kind of the same as survival mode, but it has more restrictions on placing certain blocks and destroying blocks in the game world. This mode is meant for playing in worlds where the players must solve puzzles or complete challenges.
* **player**: a selector for the players you're changing the game mode for

## 예시

Change the game mode to `creative` for all the players who are playing in `survival` mode.

```blocks
gameplay.setGameMode(
    GameMode.Creative,
    mobs.playersInGameMode(GameMode.Survival)
);
```