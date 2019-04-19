# 만들기

Creates a new ***relative*** position: *~East/~West, ~up/~down, ~North/~South*.

```sig
positions.create(0, 0, 0);
```

A relative position is the distance in each direction from the player's feet.

Read about how positions work in the [positions](/reference/positions) reference.

## 매개 변수

* **x**: the East (+x) or West (-x) distance from the player, in blocks
* **y**: the up (+y) or down (-y) distance from world player, in blocks
* **z**: the South (+z) or North (-z) distance from the player, in blocks

## 예시

Place a block of diamond above the player's head.

```blocks
blocks.place(blocks.block(Block.DiamondBlock), positions.create(0, 2, 0));
```

## 참고 항목

[`||positions:create world||`](/reference/positions/create-world)