# get Tone For Note

Get a tone from the tone gamut that matches the note you say.

```sig
sound.toneForNote(262)
```

A *gamut* is the group, or range, of tones the **Buzzer** will play. All the tones in the group are chosen ahead of time and have a certain place in the gamut (a tone number). So, you use the tones in the gamut to make your sounds. Instead of telling the **Buzzer** to play the frequency of a tone, you tell it which tone in the gamut you want to play. A tone is selected using its tone number. You get the tone number for a note using `||get tone||` with the note name.

## Parameters

* **name**: the name of the note you want a tone for.

## Example

Play a "Middle C" for 1 beat if button **A** is clicked.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.playTone(sound.toneForNote(262), BeatFraction.Whole)
})
```

## See also

[`||ring tone||`](/reference/sound/ring-tone) [`||set tempo to||`](/reference/sound/set-tempo-to)