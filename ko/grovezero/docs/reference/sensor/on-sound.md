# on Sound

Do something when the [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor") hears a quiet or loud sound.

```sig
sensor.onSound(SoundEvent.Quiet, () => {

})
```

## 매개 변수

* **event**: the sound event you want to run some code for. This is either `quiet` or `loud`.
* **이벤트 핸들러**: 소리 관련 이벤트가 발생했을 때 실행시킬 코드.

## 예시

Have the LED Matrix display a smile when it's quite. Display a sad face when it's loud.

```blocks
sensor.onSound(SoundEvent.Quiet, () => {
    display.showIcon(IconType.Smile)
})
sensor.onSound(SoundEvent.Loud, () => {
    display.showIcon(IconType.Sad)
})
```

## 참고 항목

[`||sound level||`](/reference/sensor/sound-level) [`||is sound event||`](/reference/sensor/is-sound-event)