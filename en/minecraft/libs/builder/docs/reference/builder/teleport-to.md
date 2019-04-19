# teleport To

Teleport the builder to the a new position.

```sig
builder.teleportTo(positions.create(0, 0, 0));
```

## Parameters

* **position**: the builder moves to this position

## Example

Teleport the builder someplace above the player.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
```

## See Also

In the [Build a house](/examples/house-builder) example, the builder is teleported into the world to help you build a house.