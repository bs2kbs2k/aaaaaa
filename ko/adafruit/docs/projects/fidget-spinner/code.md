# 코드 만들기

## ~avatar avatar

Light up your fidget spinner

## ~

## 활동 소요시간: ~45분

Using fast NeoPixels animations, it is possible to create a [stroboscopic effect](https://en.wikipedia.org/wiki/Stroboscopic_effect) with the fidget spinner!

## Built-in animations

Try to create programs that use the built-in animations and spin them on the fidget.

```blocks
forever(() => {
    light.showAnimation(light.rainbowAnimation, 500)
})
```

* Does it look as expected?
* `불꽃튐` 이나 `극장 체이스` 를 시험해봤나요? 

## Fun with Photon

Use the light photon to create small animation and test them out while strobing. Are you able to create cool effects?

```blocks
light.setPhotonMode(PhotonMode.PenUp)
forever(() => {
    light.photonForward(1)
})
```

* Pick your favorite photon program and try it out?

## Coarser control

At the core, photon is just turning on and off LEDs on the board. Let's get down to that point.

We start by defining a subset of the pixels (0 through 4) so that only 1 column of pixels is turned on.

```blocks
let left = light.onboardStrip().range(0, 5)
```

Then we add a [while loop](/blocks/loops/while) to repeat the animation step. A single step clears all the LEDs, turns on 1 location and increment the position counter.

```blocks
let left = light.onboardStrip().range(0, 5)
let c = 0
while (true) {
    left.clear()
    left.setPixelColor(c, 0xff0000)
    left.show()
    c = (c + 1) % left.length()
    pause(5)
}
```

https://youtu.be/oIiwwjQPurU