# on Light

Do something when the [Light Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Light Sensor") detects either darkness or light.

```sig
sensor.onLight(LightEvent.Light, function () {
    display.showIcon(IconType.Smile)
})
```

## 매개 변수

* **event**: the light event you want to run some code for. This is either `dark` or `light`.
* **이벤트 핸들러**: 빛 관련 이벤트가 발생했을 때 실행시킬 코드.

## 예시

Display a smiley face on the LED Matrix when the Light Sensor is in the light. Show a sad face when it's dark.

```blocks
sensor.onLight(LightEvent.Light, () => {
    display.showIcon(IconType.Smile)
})
sensor.onLight(LightEvent.Dark, () => {
    display.showIcon(IconType.Sad)
})
```

## 참고 항목

[`||light level||`](/reference/sensor/light-level) [`||was light triggered||`](/reference/sensor/was-light-triggered)