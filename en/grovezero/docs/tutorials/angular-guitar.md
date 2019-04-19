# Angular Guitar

## Introduction @fullscreen

Invent an instrument that plays different tones at different tilt angles!

Follow the **Angular Guitar** build instructions from the [Invention Guide](https://github.com/SeeedDocument/Bazzar_Attachment/raw/master/110060822/res/Grove%20Zero%20STEM%20Starter%20Kit%20Invention%20Guidance.pdf).

## Step 1 @fullscreen

Let's add code to play a tone in a loop.

Drag a `||sound:play tone||` block under the `||basic:forever||` block.

```blocks
loops.forever(function () {
    sound.playTone(440, BeatFraction.Quarter)
})
```

## Step 2 @fullscreen

Let's change the tone with the tilt of the guitar.

```blocks
loops.forever(function () {
    sound.playTone(sensor.acceleration(Axis.X), BeatFraction.Quarter)
})
```

## Step 3 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Tilt your guitar around!