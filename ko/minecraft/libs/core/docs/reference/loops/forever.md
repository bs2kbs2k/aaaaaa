# 무한 반복 실행

Run a part of the program in the background and keep running it over again.

```sig
loops.forever(function() {
})
```

The code you have in a `||loops:forever||` loop will run and keep repeating itself the whole time your program is active. Code in other parts of your program won't stop while your `||loops:forever||` loop is running. This includes other `||loops:forever||` loops and the [`||loops:run in background||`](/reference/control/run-in-background) block.

## 매개 변수

* **body**: the code to keep running over and over again.

## 예시

Continuously make an ice stairway. Every 2 seconds, add another ice step to the stairway.

```blocks
let y = 0
let z = 0
loops.forever(function () {
    blocks.place(blocks.block(Block.Ice), positions.create(0, y, z))
    y += 1
    z += 1
    loops.pause(2000)
})
```

## 참고 항목

[while](/blocks/loops/while), [repeat](/blocks/loops/repeat), [run in background](/reference/control/run-in-background)