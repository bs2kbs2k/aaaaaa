# rest For Beat

Rest by playing silence for the beat fraction you say.

```sig
sound.restForBeat(BeatFraction.Whole)
```

A rest is just silence (no sound at all) played for the number of beats you choose. This can be a fraction of a beat, one beat, or multiple beats.

You can read about beats and how they're measured in [`||play tone||`](/reference/sound/play-tone#how-many-beats).

## Parameters

* **beat**: the beat fraction amount to rest for. Use one of these beat fractions: >`1`, `2`, `4`, `8`, `1/2`, `1/4`, `1/8`, `1/16`

## Example

Play a "Middle C" for 1 beat when button **A** is clicked, rest for 1 beat, then play a "High B" for 1 beat.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.playTone(262, BeatFraction.Whole)
    sound.restForBeat(BeatFraction.Whole)
    sound.playTone(988, BeatFraction.Whole)
})
```

## See also

[`||ring tone||`](/reference/sound/ring-tone) [`||rest for time||`](/reference/sound/rest-for-time)