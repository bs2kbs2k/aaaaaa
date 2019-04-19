# monster

A monster mob in the game.

```sig
mobs.monster(MonsterMob.Creeper);
```

## 매개 변수

* **name**: the type of the monster

## 예시

Spawn a spider near the player.

```blocks
mobs.spawn(mobs.monster(MonsterMob.Spider), positions.create(5, 0, 0))
```

## 참고 항목

[`||mobs:spawn||`](/reference/mobs/spawn)