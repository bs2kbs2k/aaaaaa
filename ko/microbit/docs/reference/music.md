# 소리

`P0` 핀을 통해 소리(음)를 출력합니다.

```cards
music.playTone(0, 0);
music.ringTone(0);
music.rest(0);
music.beginMelody(music.builtInMelody(Melodies.Entertainer), MelodyOptions.Once);
music.onEvent(MusicEvent.MelodyNotePlayed, () => {});
music.beat(BeatFraction.Whole);
music.tempo();
music.changeTempoBy(20);
music.setTempo(120);
```

## 참고 항목

[소리 출력](/reference/music/play-tone), [소리 출력(Hz)](/reference/music/ring-tone), [지속 시간(ms)](/reference/music/rest), [소리 출력 멜로디](/reference/music/begin-melody), [소리 감지하면 실행](/reference/music/on-event), [박자](/reference/music/beat), [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by), [빠르기(bpm) 설정](/reference/music/set-tempo),