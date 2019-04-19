# kill

Kills all the mobs you select.

```sig
mobs.kill(
    mobs.target(TargetSelectorKind.AllEntities)
);
```

## 매개 변수

* **target**: a selector that chooses which mobs are killed.

## 예시

Kill all the creepers near the current player.

```blocks
mobs.kill(
    mobs.near(
        mobs.entitiesByType(mobs.monster(MonsterMob.Creeper)),
        player.position(),
        10
    )
)
```

### 참고 항목

[`||mobs:on mob killed||`](/reference/mobs/on-mob-killed)