# Reference

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

### See Also

[player](/reference/player), [mobs](/reference/mobs), [agent](/reference/agent), [builder](/reference/builder), [gameplay](/reference/gameplay), [blocks](/reference/blocks), [positions](/reference/positions), [shapes](/reference/shapes)

```package
builder
shapes
```