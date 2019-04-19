# random

Pick a random position inside a cube shaped space.

```sig
positions.random(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
```

You set the corners of the space (volume) where the random position is chosen. The corners determine where, and how big, the cube shaped space is.

## Parameters

* **p1**: the position of the first corner of the cube.
* **p2**: the position of the opposite corner of the cube.

## Example

Spawn chickens at random positions above the player's head.

```blocks
for (let i = 0; i < 10; i++) {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.random(
        positions.create(-3, 5, -3),
        positions.create(3, 10, 3)
    ));
}
```