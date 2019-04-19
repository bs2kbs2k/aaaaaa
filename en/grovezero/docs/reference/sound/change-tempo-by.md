# change Tempo By

Make the tempo (speed) of the sound playing go faster or slower.

```sig
sound.changeTempoBy(0)
```

The current tempo (beats per minute, or bpm) will change by the amount you say. If sound is playing at 120 bpm and you want to speed it up two times faster, just add another 120 bpm:

```block
sound.changeTempoBy(120)
```

Or, how about this, add the current tempo:

```block
sound.changeTempoBy(sound.getTempo())
```

If you want to slow the tempo down, use a negative number. To slow the tempo by 20 bpm:

```block
sound.changeTempoBy(-20)
```

## Parameters

* `bpm`: a [number](/types/number) that says how much to change the bpm (beats per minute, or number of beats in a minute of the sound that the Buzzer is playing). You can choose a number of beats between `60` and `960`.

## Example

Play a "Middle C" at 120bpm when button **A** is clicked. When button **B** is clicked, the add 10 bpm to the tempo.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.ringTone(262)
    sound.setTempoTo(120)
})
input.onButton(Button.B, ButtonEvent.Click, function () {
    sound.changeTempoBy(10)
})
```

## See also

[`||get tempo||`](/reference/sound/get-tempo) [`||set tempo to||`](/reference/sound/set-tempo-to)