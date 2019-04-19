# turn

Turn the builder to the `left` or to the `right`.

```sig
builder.turn(TurnDirection.Left);
```

## 매개 변수

* **direction**: the direction of the turn, eg: TurnDirection.Left

## 예시

Make the builder turn in a full circle with 4 turns.

```blocks
for (let i = 0; i < 4; i++) {
    builder.turn(TurnDirection.Right);
}
```

## 참고 항목

[`||builder:face||`](/reference/builder/face)

You can see the builder make some turns in the [Build a house](/examples/house-builder) example.