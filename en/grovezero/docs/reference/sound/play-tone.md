# play Tone

Play a tone on the [Buzzer](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Buzzer") for a some number of beats.

```sig
sound.playTone(262, BeatFraction.Whole)
```

## Pick a tone

In the blocks editor you can choose a tone from a piano keyboard that appears when you go to change the tone in the block. You can also just type the tone frequency in the block too.

## How many beats

The tone is played for some amount of time measured as *beats*. You choose a *beat fraction* to say how many beats long you want to play the tone. The beat fraction can be a part of a beat, a whole beat, or multiple beats.

The standard number of *beats per minute* (bpm) in music is 120 bpm which is one-half of a second. A *whole* note lasts for 4 beats and a *quarter* note takes just one beat.

## Parameters

* **frequency**: the frequency of the tone you want to play. This is measured in Hz.
* **beat**: the beat fraction, how may beats you to play the tone for: >`1/16`, `1/8`, `1/4`, `1`, `2`, `4`, or `8`

## Example

Play a "Middle C" tone on the Buzzer for 1 beat if button **A ** is clicked.

```blocks
input.onButton(Button.A, ButtonEvent.Click, () => {
    sound.playTone(262, BeatFraction.Whole)
})
```

## See also

[`||ring tone||`](/reference/sound/ring-tone) [`||set tempo to||`](/reference/sound/set-tempo-to)