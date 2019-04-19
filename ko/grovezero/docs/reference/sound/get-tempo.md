# get Tempo

Get the current tempo in beats per minutes (bpm).

```sig
sound.getTempo()
```

## 리턴값

* a [number](/types/number) that is the beats per minute current set for playing sounds. It will be a value between `60` and `960`.

## 예시

When button **A** is clicked, add 60 bpm to the tempo. If button **B** is clicked, subtract 60 bpm from the current tempo. When button **A+B** is clicked, the Buzzer plays a tone at the latest tempo setting.

Also, show the current tempo value on the LED Matrix.

```blocks
input.onButton(Button.A, ButtonEvent.Click, function () {
    sound.changeTempoBy(60)
    display.showNumber(sound.getTempo())
})
input.onButton(Button.B, ButtonEvent.Click, function () {
    sound.changeTempoBy(-60)
    display.showNumber(sound.getTempo())
})
input.onButton(Button.AB, ButtonEvent.Click, function () {
    sound.playTone(262, BeatFraction.Whole)
})
sound.setTempoTo(120)
```

## 참고 항목

[`||set tempo to||`](/reference/sound/set-tempo-to) [`||change tempo by||`](/reference/sound/change-tempo-by)