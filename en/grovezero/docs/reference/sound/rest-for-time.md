# rest For Time

Rest by playing silence for a some amount to time.

```sig
sound.restForTime(100)
```

A rest is just silence (no sound at all) played for the number of milliseconds you choose.

## Parameters

* **time**: the amount of time to rest for. The time value is in milliseconds (ms) which is 1/1000 of second.

## Example

Play a "Middle C" for 1 beat when button **A** is clicked, rest for 500ms, then play "High B" for 1 beat.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.playTone(262, BeatFraction.Whole)
    sound.restForTime(500)
    sound.playTone(988, BeatFraction.Whole)
})
```

## See also

[`||rest beat||`](/reference/sound/rest-beat) [`||set tempo to||`](/reference/sound/set-tempo-to)