# Fast Forward

## Introduction @unplugged

Nobody can stop the pace of time. In this tutorial, though, you will make time go faster than normal.

![Fast forwarding!](/static/tutorials/fast-forward.gif)

## 단계 1

Rename **"run"** to **"ff"** in the `||player:on chat command||` block.

```blocks
player.onChat("ff", function () {
})
```

## 단계 2

Place a `||gameplay:time add||` block with `10000` ticks in your chat command.

A *Minecraft day* lasts 24000 ticks for 20 minutes of play. Let's speed it up by skipping **10000** ticks.

```blocks
player.onChat("ff", function () {
    gameplay.timeAdd(100)
})
```

## 단계 3

Go to Minecraft, press **t** to open the chat and enter **ff**.

Time not changing? Make sure the "always day" option isn't turned on.

## 단계 4

Place a `||loops:repeat||` block around the `||gameplay:time add||` block to repeat `240` times adding `100` ticks.

By adding **240** times x **100** ticks, we will advance time by **24000**... which is one day in Minecraft!

```blocks
player.onChat("ff", function () {
    for(let i = 0; i < 240;i++) {
        gameplay.timeAdd(100)
    }
})
```

## 단계 5

Go to Minecraft and enter **ff**. Look at the Sun and the Moon chasing each other.