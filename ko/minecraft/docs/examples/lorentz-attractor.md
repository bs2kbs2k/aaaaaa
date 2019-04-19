# 나비효과

![A lorentz attractor drawn in the sky](/static/mods/lorentz-attractor.jpg)

A mysterious [Lorentz Attractor](https://wikipedia.org/wiki/Lorenz_system). A strange occurrence swirling in the sky.

## ~ hint

This code originally came from [TouchDevelop](https://www.touchdevelop.com). You can see that project at: [LorentzAttractor](https://www.touchdevelop.com/qrfn).

## ~

## Try the code:

```blocks
let deltat = 0
let sigma = 0
let ro = 0
let beta = 0
let x = 0
let y = 0
let z = 0
let ax = 0
let ay = 0
let az = 0
let block = 0
let p: Position = null
let pb: Position = null

player.onChat("lorentz", function () {
    x = 10
    y = 0
    z = 10
    p = player.position()
    while (true) {
        ax = x
        ay = y
        az = z
        x = sigma * (ay - ax) * deltat + ax
        y = (ax * (ro - az) - ay) * deltat + ay
        z = (ax * ay - beta * az) * deltat + az
        pb = positions.add(
        p,
        positions.create(x * 3, 10, z * 3)
        )
        blocks.place(block, pb)
    }
})

deltat = 0.01
sigma = 10
ro = 28
beta = 2.6667
block = blocks.block(Block.Glowstone)
```