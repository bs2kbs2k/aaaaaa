# 소리 이벤트 감지하면 실행

소리나 멜로디 이벤트가 발생했을 때, 실행할 작업을 설정할 수 있습니다.

```sig
music.onEvent(MusicEvent.MelodyNotePlayed, () => {})
```

## 매개 변수

* `값`. 소리 이벤트 종류
* `처리기` 해당 소리 이벤트가 발생했을 때, 실행시킬 코드.

## 예시

다음은 모든 소리 이벤트를 시리얼통신으로 전송하는 예시입니다.

```blocks
music.onEvent(MusicEvent.MelodyRepeated, () => {
    serial.writeLine("melody repeated")
})
music.onEvent(MusicEvent.MelodyEnded, () => {
    serial.writeLine("melody ended")
})
music.onEvent(MusicEvent.MelodyStarted, () => {
    serial.writeLine("melody started")
})
music.onEvent(MusicEvent.MelodyRepeated, () => {
    serial.writeLine("background melody repeated")
})
music.onEvent(MusicEvent.BackgroundMelodyStarted, () => {
    serial.writeLine("background started")
})
music.onEvent(MusicEvent.BackgroundMelodyEnded, () => {
    serial.writeLine("background ended")
})
music.onEvent(MusicEvent.BackgroundMelodyPaused, () => {
    serial.writeLine("background paused")
})
music.onEvent(MusicEvent.BackgroundMelodyResumed, () => {
    serial.writeLine("background resumed")
})
music.onEvent(MusicEvent.BackgroundMelodyRepeated, () => {
    serial.writeLine("background repeated")
})
input.onButtonPressed(Button.A, () => {
    music.beginMelody(music.builtInMelody(Melodies.BaDing), MelodyOptions.Once)
})
music.setTempo(100)
music.beginMelody(music.builtInMelody(Melodies.Ringtone), MelodyOptions.ForeverInBackground)
```