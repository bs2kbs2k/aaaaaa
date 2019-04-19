# Fast Forward

![Daytime changing quickly](/static/mods/fast-forward.jpg)

Time never stops but you can make it go faster!

## Try the code:

```blocks
player.onChat("ff", function () {
    for(let i = 0; i < 240;i++) {
        gameplay.timeAdd(100)
    }
})
```