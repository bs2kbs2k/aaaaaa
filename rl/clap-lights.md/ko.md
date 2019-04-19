# Clap lights

## 단계 1 @fullscreen

Drag a `||input:on loud sound||` block into the workspace. It will run some code inside when a clap is detected by the microphone.

```blocks
input.onLoudSound(function () {
})
```

## 단계 2

Drag the `||light:set brightnesss||` and `||light:set all pixels||` blocks into `||input:on loud sound||` to turn the lights **ON** really bright. Make the pixel color `white` an set the brightness to `255`.

```blocks
input.onLoudSound(function () {
    light.setBrightness(255)
    light.setAll(0xffffff)
})
```

## 단계 3

Click `|Download|` to transfer your code to the @boardname@. Try clapping to see if the lights turn on!

## 단계 4

Drag a `||loops:pause||` block to wait 2 seconds, and another `||light:set all pixels||` block to turn **OFF** the lights after that. Make the pixel color `black` for the second `||light:set all pixels||`.

```blocks
input.onLoudSound(function () {
    light.setBrightness(255)
    light.setAll(0xffffff)
    pause(2000)
    light.setAll(0x000000)
})
```

## 단계 5

Click `|Download|` again to transfer your code to the @boardname@. Try clapping to see if the lights turn on and then off after a while.

## 단계 6

Awesome! Congratulations on completing this challenge on the @boardname@.

![clap lights on](/static/cp/tutorials/clap-lights/clap-on-off.gif)