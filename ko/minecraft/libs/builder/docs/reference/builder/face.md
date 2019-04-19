# face

Make the builder face in a certain direction.

```sig
builder.face(CompassDirection.West);
```

The builder faces in the direction it is turned and the builder works in the direction it faces. So, if you want the builder to work in a different direction than where it turned to, you use `||builder:face||` to change it.

## 매개 변수

* **direction**: the direction the builder will face after a turn

## 예시

Make the builder turn in a random direction and then make it face North. No matter where the builder was facing after the last turn, at the end it will face North.

```blocks
for (let i = 0; i < Math.randomRange(0, 5); i++) {
    builder.turn(TurnDirection.Right);
}
builder.face(CompassDirection.North);
```

## 참고 항목

You can see the builder do its work in the [Build a house](/examples/house-builder) example.