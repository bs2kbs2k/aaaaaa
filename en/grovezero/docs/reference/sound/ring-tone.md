# ringTone

Play a tone continuously.

```sig
sound.ringTone(sound.toneToNote(262))
```

This is like [`||play tone||`](/reference/soune/play-tone) except there is no beat time. The tone just keeps playing.

## Pick a tone

In the blocks editor you can choose a tone from a piano keyboard that appears when you go to change the tone in the block. You can also just type the tone frequency in the block too.

## Parameters

* **frequency**: the frequency of the tone you want to play. This is measured in Hz.

## Example

Ring the tone of "Middle C" on the continuously on the Buzzer when button **A** is clicked.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.ringTone(262)
})
```

## See also

[`||play tone||`](/reference/sound/play-tone) [`||set tempo to||`](/reference/sound/set-tempo-to)