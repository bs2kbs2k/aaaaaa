# One-eyed Guost

## Introduction @fullscreen

Make a creepy little ghost that sleeps at day and awakes at night!

Follow the **One-eyed Ghost** build instructions from the [Invention Guide](https://github.com/SeeedDocument/Bazzar_Attachment/raw/master/110060822/res/Grove%20Zero%20STEM%20Starter%20Kit%20Invention%20Guidance.pdf).

![One-eyed Circuit](/static/invention-guide/one-eyed-ghost/circuit.png)

## Step 1 @fullscreen

Let's show an eye when it gets dark.

Drag a `||sensor:on light dark||` block in the code workspace.

```blocks
sensor.onLight(LightEvent.Dark, function () {
})
```

## Step 2 @fullscreen

Drag a `||display:show leds||` block under the `||sensor:on light dark||` and paint an eye.

```blocks
sensor.onLight(LightEvent.Dark, function () {
    display.showLeds(
    `
        . . . . . 
        . # # # . 
        # . . . # 
        # . # . # 
        # . . . # 
        . # # # .
        `
    )
})
```

## Step 3 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Try waiving your hand over the Light Sensor to display the eye!

## Step 4 @fullscreen

Let's show turn off the display when it gets light.

Drag a `||sensor:on light light||` and block in the code workspace. Place another `||display:show leds||` block to turn off all LEDs.

```blocks
sensor.onLight(LightEvent.Light, function () {
    display.showLeds(
    `
        . . . . . 
        . . . . . 
        . . . . . 
        . . . . . 
        . . . . . 
        . . . . .
        `
    )    
})
```

## Step 5 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Try waiving your hand over the Light Sensor to display the eye and turn it off.