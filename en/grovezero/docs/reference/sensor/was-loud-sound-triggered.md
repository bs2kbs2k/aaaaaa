# was loud Sound triggered

Get the last [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") event and see if it detected a loud sound.

```sig
sensor.wasLoudSoundTriggered()
```

## Returns

* a [boolean](/types/boolean) value that is `true` if the sound event happened, or `false` if not.

## Example

Show the smiley face when the sensor hears in loud environment. If it's quiet, display a sad face.

```blocks
loops.forever(function () {
    if (sensor.wasLoudSoundTriggered()) {
        display.showIcon(IconType.Smile)
    } else {
        display.showIcon(IconType.Sad)
    }
})
```

## See also

[`||on sound||`](/reference/sensor/on-loud-sound) [`||sound level||`](/reference/sensor/sound-level)