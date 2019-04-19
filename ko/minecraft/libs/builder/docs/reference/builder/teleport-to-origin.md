# teleport To Origin

Teleport the builder to its origin.

```sig
builder.teleportToOrigin();
```

The origin is the first place where the builder was teleported to. Also, the origin for the builder is changed to some other place with [`||builder:set origin||`](/reference/bulder/set-origin). The origin is as a point of reference for the builder. This like making a home base for the builder. After you set an origin, you can easily return the builder there.

This is really useful when the builder is making something complicated and you want the builder to start again at the original spot or do something new.

## 예시

Set the builder's origin to the player's position. Move the builder away...bring the builder back to the origin.

```blocks
builder.teleportTo(positions.create(0, 0, 0));
builder.setOrigin();
builder.move(SixDirection.Forward, 5);
builder.teleportToOrigin();
```

## 참고 항목

[`||builder:set origin||`](/reference/builder/set-origin)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).