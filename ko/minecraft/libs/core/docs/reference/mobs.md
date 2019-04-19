# 몹

**Mobs** are beings, or entities, in a Minecraft world. They are the players, the monsters, the villagers, etc... Mobs can be spanwed, killed, teleported, enchanted, and given items.

### Types

A mob type is identifed by a unique number. Various helpers like `||mobs:animal||` or `||mobs:monster||` are there to help you craft the mob you want.

### Seletors

**Selectors** allow you to describe and select a group of mobs at once. For example, you can decide to `select all players` or `select all chickens`. Selection can be made by mob type, distance and other criterias. Various helpers like `||mobs:add rule||` help with crafting advanced selectors.

## 찾아보기

```cards
mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, 0));
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), () => {

});
mobs.kill(
    mobs.target(TargetSelectorKind.AllEntities)
);
mobs.animal(AnimalMob.Pig);
mobs.monster(MonsterMob.Creeper);
mobs.projectile(ProjectileMob.LightningBolt);
```

## 셀렉터

```cards
mobs.target(TargetSelectorKind.LocalPlayer);
mobs.near(
    mobs.target(TargetSelectorKind.LocalPlayer),
    positions.create(0, 0, 0),
    5
);
mobs.entitiesByType(mobs.animal(AnimalMob.Chicken));
mobs.playerByName("");
mobs.playersInGameMode(GameMode.Survival);
mobs.target(TargetSelectorKind.AllEntities).atCoordinate(positions.create(0, 0, 0));
mobs.target(TargetSelectorKind.AllEntities).withinRadius(0);
mobs.target(TargetSelectorKind.AllEntities).outsideRadius(0);
mobs.target(TargetSelectorKind.AllEntities).addRule("type", "chicken");
mobs.target(TargetSelectorKind.AllEntities).toString();
```

## 고급

```cards
mobs.teleportToPosition(
    mobs.target(TargetSelectorKind.LocalPlayer),
    positions.create(0, 0, 0)
);
mobs.teleportToPlayer(
    mobs.target(TargetSelectorKind.LocalPlayer),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
mobs.enchant(mobs.target(TargetSelectorKind.LocalPlayer), "infinity", 1);
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.block(Block.Grass),
    1
);
mobs.execute(
    mobs.target(TargetSelectorKind.LocalPlayer),
    positions.create(0, 0, 0),
    ""
);
mobs.executeDetect(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    "say Hi!"
);
```