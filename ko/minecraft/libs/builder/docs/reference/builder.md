# 빌더

The builder is a tool that makes it easier to build complex structures in the game.

빌더는 월드 안에서 이동시킬 수 있는 보이지 않는 투명 커서입니다. 빌더의 이동 경로와 마크를 이용해, 여러 개의 블록들을 게임 월드에 배치시킬 수 있습니다.

To see an example project that uses the builder, see the [Build a house](/examples/house-builder) example.

## 찾아보기

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

## 고급

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
빌더
```