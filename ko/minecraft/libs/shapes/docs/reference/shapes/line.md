# 선

시작 위치부터 끝 위치까지 선 모양을 만듭니다.

```sig
shapes.line(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
```

## 매개 변수

* **p1**: the position of the start of the line
* **p2**: the position of the end of the line

## 예시

Draw a diagonal line of gold from the player to a position `10` blocks to the East and `10` blocks to the North.

```blocks
player.onChat("diag", function () {
    shapes.line(
        blocks.block(Block.GoldBlock),
        positions.create(0, 1, 0),
        positions.create(10, 1, 10)
    )
})
```

## 참고 항목

[`||builder:builder line||`](/reference/builder/line)