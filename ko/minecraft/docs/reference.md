# 찾아보기

The mods you create are built with code blocks made to interact with Minecraft. Blocks are grouped together based on which part of the Minecraft world they relate to. The block group has its own color. That way you know which group a block belongs to.

```namespaces
player.say("Hi!");
blocks.fill(blocks.block(Block.TNT), positions.create(0,0,0) , positions.create(0,0,0));
mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0,0,0));
agent.destroy(SixDirection.Forward);
builder.line(Block.Glass);
gameplay.setGameMode(GameMode.Survival, mobs.target(TargetSelectorKind.NearestPlayer));
positions.create(0, 0, 0);
shapes.line(Block.Dirt, positions.create(1,1,1), positions.create(2,3,3));
```

### 참고 항목

[플레이어](/reference/player), [몹](/reference/mobs), [에이전트](/reference/agent), [빌더](/reference/builder), [게임 플레이](/reference/gameplay), [블록](/reference/blocks), [위치](/reference/positions), [모양](/reference/shapes)

```package
builder
shapes
```