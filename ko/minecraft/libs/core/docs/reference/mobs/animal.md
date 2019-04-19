# 동물

An animal mob in the game.

```sig
mobs.animal(AnimalMob.Pig);
```

## 매개 변수

* **name**: the type of animal

## 예시

Spawn a sheep near the player.

```blocks
mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(1, 0, 0));
```

## 참고 항목

[`||mobs:spawn||`](/reference/mobs/spawn)