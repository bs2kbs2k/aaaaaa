# Shapes

Fill lines, circles, and other geometric objects with **shapes**. Use them to easily make parts for your structures.

## Reference

```cards
shapes.line(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
shapes.circle(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    0,
    Axis.X,
    ShapeOperation.Replace
);
shapes.sphere(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    0,
    ShapeOperation.Replace
);
```

```package
shapes
```