# 이동

Move the builder in the direction you want it to go. You tell the builder how many blocks to move in that direction.

```sig
builder.move(SixDirection.Forward, 1);
```

## 매개 변수

* **direction**: the direction that the builder moves, eg: SixDirection.Forward
* **blocks**: how far the builder moves, in blocks, eg: 1

## 예시

Move the builder up 5 blocks.

```blocks
builder.move(SixDirection.Up, 5);
```

## 참고 항목

[`||builder:shift||`](/reference/builder/shift)

You can see the builder do some moves in the [Build a house](/examples/house-builder) example.