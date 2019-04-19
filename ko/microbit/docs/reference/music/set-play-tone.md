# 소리 출력 설정

[소리 출력](/reference/music/play-tone) 대신 사용할 수 있습니다.

```sig
music.setPlayTone((frequency: number, duration: number) => {})
```

## 매개 변수

* `f`. 교체 함수.

## 예시

다음은 무선 라디오 기능을 이용해 진동수와 지속 시간을 전송하고, 그 신호를 받은 @boardname@ 에서 무선으로 그 음을 출력하는 예시입니다.

```typescript
input.onButtonPressed(Button.A, () => {
    music.playTone(440, 120)
    led.toggle(0, 0)
})
radio.onDataPacketReceived( ({ receivedNumber }) =>  {
    const freq = receivedNumber >> 16;
    const duration = receivedNumber & 0xffff;
    music.playTone(freq, duration);
})
input.onButtonPressed(Button.B, () => {
    music.setPlayTone((frequency: number, duration: number) => {
        radio.sendNumber((frequency << 16) | (duration & 0xffff));
    })    
})
```

## 참고 항목

[지속 시간(ms)](/reference/music/rest), [소리 출력(Hz)](/reference/music/ring-tone) , [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)