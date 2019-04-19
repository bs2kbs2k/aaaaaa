# set Origin

Set the builder's origin to the builder's current location.

```sig
builder.setOrigin();
```

The origin acts as a point of reference for the builder. This like making a home base for the builder. After you set an origin, you can easily return the builder there.

This is really useful when the builder is making something complicated and you want the builder to start again at the same spot or do something new.

## Example

Set the builder's origin to the player's position. Move the builder away...bring the builder back to the origin.

```blocks
builder.teleportTo(positions.create(0, 0, 0));
builder.setOrigin();
builder.move(SixDirection.Forward, 5);
builder.teleportToOrigin();
```

## See Also

[`||builder:teleport to origin||`](/reference/builder/teleport-to-origin)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).