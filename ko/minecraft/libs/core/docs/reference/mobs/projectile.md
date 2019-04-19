# 마법발사

게임에서 마법발사하기

```sig
mobs.projectile(ProjectileMob.LightningBolt);
```

## 매개 변수

* **name**: the type of the projectile

## 예시

Trigger lightning near the player.

```blocks
mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(5, 0, 0))
```

## 참고 항목

[`||mobs:spawn||`](/reference/mobs/spawn)