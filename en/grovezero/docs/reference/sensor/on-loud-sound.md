# on loud Sound

Do something when the [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") hears a quiet or loud sound.

```sig
sensor.onLoudSound(() => {

})
```

## Parameters

* **handler**: the code to run when the sound event happens.

## Example

Have the LED Matrix display a smile when it detects a loud sound.

```blocks
sensor.onLoudSound(() => {
    display.showIcon(IconType.Smile)
})
```

## See also

[`||sound level||`](/reference/sensor/sound-level) [`||was loud sound triggered||`](/reference/sensor/was-loud-sound-triggered)