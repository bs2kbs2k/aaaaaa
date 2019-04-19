# teleport To

Teleport the builder to the a new position.

```sig
builder.teleportTo(positions.create(0, 0, 0));
```

## 매개 변수

* **position**: the builder moves to this position

## 예시

Teleport the builder someplace above the player.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
```

## 참고 항목

In the [Build a house](/examples/house-builder) example, the builder is teleported into the world to help you build a house.