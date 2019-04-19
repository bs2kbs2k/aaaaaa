# rest For Time

Rest by playing silence for a some amount to time.

```sig
sound.rest(100)
```

A rest is just silence (no sound at all) played for the number of milliseconds you choose.

## 매개 변수

* **time**: the amount of time to rest for. The time value is in milliseconds (ms) which is 1/1000 of second.

## 예시

Play a "Middle C" for 1 beat when button **A** is clicked, rest for 500ms, then play "High B" for 1 beat.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.playTone(262, BeatFraction.Whole)
    sound.rest(500)
    sound.playTone(988, BeatFraction.Whole)
})
```

## 참고 항목

[`||set tempo to||`](/reference/sound/set-tempo-to)