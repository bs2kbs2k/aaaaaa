# kill

Kills all the mobs you select.

```sig
mobs.kill(
    mobs.target(TargetSelectorKind.AllEntities)
);
```

## Parameters

* **target**: a selector that chooses which mobs are killed.

## Example

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

### See also

[`||mobs:on mob killed||`](/reference/mobs/on-mob-killed)