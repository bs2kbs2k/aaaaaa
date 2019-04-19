# 위치마크

Mark the current builder's position.

```sig
builder.mark();
```

The mark is the position is the where the builder is at the moment. The mark sets the beginning position for various builder activities. When the builder makes a line, for example, the mark is place where the line will start. If the builder moves somewhere away from the mark, a line is traced between where the mark is and the builder's current position.

## 예시

Use a position **mark** to trace a line of stone near the player.

```blocks
builder.teleportTo(positions.create(0, 0, 0));
builder.mark();
builder.move(SixDirection.Forward, 5);
builder.line(blocks.block(Block.Stone));
```

## 참고 항목

Here's an example project that uses the builder: [Build a house](/examples/house-builder).