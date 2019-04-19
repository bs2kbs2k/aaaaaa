# copy

Copy all the blocks in the space from the builder's **mark** to the current position.

```sig
builder.copy();
```

This copies the blocks in a cube shaped space which starts from the **mark** position and goes to where the builder is now. New blocks aren't created until [`||builder:paste||`](/reference/builder/paste) is used.

## 예시

Create a ceiling above the player by copying the floor beneath the player.

```blocks
builder.teleportTo(positions.create(2, -1, 2));
builder.mark();
builder.teleportTo(positions.create(-2, -1, -2));
builder.copy();
builder.teleportTo(positions.create(-2, 2, -2));
builder.paste();
```

## 참고 항목

[`||builder:paste||`](/reference/builder/paste)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).