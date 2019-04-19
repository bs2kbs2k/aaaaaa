# set Tempo To

Set the tempo to some number of beats per minutes (bpm).

```sig
sound.setTempoTo(120)
```

The default tempo is 120bpm. You can change the tempo to make sounds play faster or slower. More bpm, the sound is faster. Less bpm, the sound is slower.

You can read about beats and how they're measured in [`||play tone||`](/reference/sound/play-tone#how-many-beats).

## Parameters

* **bpm**: a [number](/types/number) of beats per minute to play sound at. The bpm values are from `60` to `960`.

## Example

Ring the tone of "Middle C" when button **A** is clicked. When button **B** is clicked, change the tempo to 120bpm.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.ringTone(262)
})
input.onButton(Button.B, ButtonEvent.Click, function () {
    sound.setTempoTo(120)
})
```

## See also

[`||ring tone||`](/reference/sound/ring-tone) [`||change tempo by||`](/reference/sound/change-tempo-by)