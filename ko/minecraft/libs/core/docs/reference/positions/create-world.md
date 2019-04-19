# 월드 만들기

Create a new ***world***, (absolute), position: *East/West, up/down, North/South*.

```sig
positions.createWorld(0, 0, 0);
```

A ***world*** position is the distance in each direction from the world's origin, which is **(0, 0, 0)**. The distance is measured in blocks.

Read about how positions work in the [positions](/reference/positions) reference.

## 매개 변수

* **x**: the East (+x) or West (-x) distance from world coordinate **0**, in blocks
* **y**: the up (+y) or down (-y) distance from world coordinate **0**, in blocks
* **z**: the South (+z) or North (-z) distance from world coordinate **0**, in blocks

## 예시

Teleport the player to a new world position that is `10` blocks above the world origin.

```blocks
player.onChat("jump", function () {
    player.teleport(positions.createWorld(0, 10, 0))
})
```

## 참고 항목

[`||positions:create||`](/reference/positions/create)