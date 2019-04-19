# paste

Paste the blocks copied earlier using [`||builder:copy||`](/reference/builder). The blocks are pasted at the builder's current position.

```sig
builder.paste();
```

## 예시

Create a ceiling above the player by pasting blocks copied from the floor beneath the player.

```blocks
builder.teleportTo(positions.create(2, -1, 2));
builder.mark();
builder.teleportTo(positions.create(-2, -1, -2));
builder.copy();
builder.teleportTo(positions.create(-2, 2, -2));
builder.paste();
```

## 참고 항목

[`||builder:copy||`](/reference/builder/copy)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).