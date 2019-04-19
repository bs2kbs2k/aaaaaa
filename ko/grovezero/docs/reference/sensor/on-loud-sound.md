# on loud Sound

Do something when the [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") hears a quiet or loud sound.

```sig
sensor.onLoudSound(() => {

})
```

## 매개 변수

* **이벤트 핸들러**: 소리 관련 이벤트가 발생했을 때 실행시킬 코드.

## 예시

Have the LED Matrix display a smile when it detects a loud sound.

```blocks
sensor.onLoudSound(() => {
    display.showIcon(IconType.Smile)
})
```

## 참고 항목

[`||sound level||`](/reference/sensor/sound-level) [`||was loud sound triggered||`](/reference/sensor/was-loud-sound-triggered)