# set difficulty

Set the difficulty level for gameplay.

```sig
gameplay.setDifficulty(GameDifficulty.Peaceful);
```

## 매개 변수

* **difficulty**: the new difficulty level for the game. The levels are: >`peaceful`: monsters cannot spawn and you get more hearts quickly  
    `easy`: easy gameplay level  
    `normal`: normal gameplay level  
    `hard`: the really difficult gameplay level  
    

## 예시

Spawn a new monster. However, the monster won't spawn if the game is currently set to peaceful, so change the gameplay to `easy` before spawning. Change it to `normal`, or even `hard` for a greater challenge!

```blocks
player.onChat("creeper", function () {
    gameplay.setDifficulty(GameDifficulty.Easy)
    mobs.spawn(mobs.monster(MonsterMob.Creeper), positions.create(0, 0, 0))
})
```