# spawn

Bring a creature into the game at a position you choose.

```sig
mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, 0));
```

## 매개 변수

* **mob**: the type of creature to bring in.
* **destination**: the position to bring the creature into the game at.

## 예시

Spawn on a cow near the current player. Moo!

```blocks
mobs.spawn(mobs.animal(AnimalMob.Cow), positions.create(1, 0, 0));
```

## 참고 항목

[`||mobs:animal||`](/reference/mobs/animal), [`||mobs:monster||`](/reference/mobs/monster)