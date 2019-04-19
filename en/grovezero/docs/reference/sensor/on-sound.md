# on Sound

Do something when the [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") hears a quiet or loud sound.

```sig
sensor.onSound(SoundEvent.Quiet, () => {

})
```

## Parameters

* **event**: the sound event you want to run some code for. This is either `quiet` or `loud`.
* **handler**: the code to run when the sound event happens.

## Example

Have the LED Matrix display a smile when it's quite. Display a sad face when it's loud.

```blocks
sensor.onSound(SoundEvent.Quiet, () => {
    display.showIcon(IconType.Smile)
})
sensor.onSound(SoundEvent.Loud, () => {
    display.showIcon(IconType.Sad)
})
```

## See also

[`||sound level||`](/reference/sensor/sound-level) [`||is sound event||`](/reference/sensor/is-sound-event)