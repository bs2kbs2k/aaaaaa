# is Sound Event

Get the last [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") event and see if the sound was quiet or loud.

```sig
sensor.isSoundEvent(SoundEvent.Quiet)
```

## Parameters

* **event**: the sound event you want to check for. You can check if the sound was either `quiet` or `loud`.

## Returns

* a [boolean](/types/boolean) value that is `true` if the sound event happened, or `false` if not.

## Example

Show the smiley face when the sensor hears in quiet environment. If it's loud, display a sad face.

```blocks
loops.forever(function () {
    if (sensor.isSoundEvent(SoundEvent.Quiet)) {
        display.showIcon(IconType.Smile)
    } else {
        display.showIcon(IconType.Sad)
    }
})
```

## See also

[`||on sound||`](/reference/sensor/on-sound) [`||sound level||`](/reference/sensor/sound-level)