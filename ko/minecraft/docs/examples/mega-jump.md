# 메가 점프

![Jumping far away into the sky](/static/mods/mega-jump.jpg)

Make a jump command to send yourself as far up as you want.

## Try the code:

```blocks
player.onChat("jump", function (num1) {
    player.teleport(positions.create(0, num1, 0))
})
```