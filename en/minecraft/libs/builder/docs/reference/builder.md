# Builder

The builder is a tool that makes it easier to build complex structures in the game.

The builder is an invisible cursor that you can move around in the world. You can then place multiple blocks at once in the game world, based on the builder's trajectory and marks.

To see an example project that uses the builder, see the [Build a house](/examples/house-builder) example.

## Reference

```cards
builder.move(SixDirection.Forward, 1);
builder.turn(TurnDirection.Left);
builder.face(CompassDirection.West);
builder.teleportTo(positions.create(0, 0, 0));
builder.setOrigin();
builder.teleportToOrigin();
builder.mark();
builder.place(blocks.block(Block.Grass));
builder.tracePath(blocks.block(Block.Grass));
builder.fill(blocks.block(Block.Grass));
```

## Advanced

```cards
builder.position();
builder.raiseWall(blocks.block(Block.Grass), 5);
builder.line(blocks.block(Block.Grass));
builder.copy();
builder.paste();
builder.pushState();
builder.popState();
builder.shift(1, 1, 1);
```

```package
builder
```