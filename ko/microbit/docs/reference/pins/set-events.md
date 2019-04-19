# 이벤트 발생 설정

지정한 핀으로 발생하는 이벤트를 설정합니다.

```sig
pins.setEvents(DigitalPin.P0, PinEventType.Edge);
```

## 매개 변수

* `name`. 설정할 @boardname@ 핀 (`P0` 부터 `P20`)
* `type`. 핀 연결을 통해 발생시킬 이벤트 종류

## 예시

다음은 `P0` 핀에 의해서 발생되는 이벤트를 설정하는 예시입니다.

```blocks
control.onEvent(control.eventSourceId(EventBusSource.MICROBIT_ID_IO_P0),  control.eventValueId(EventBusValue.MICROBIT_PIN_EVT_RISE), () => {
    basic.showString("Rise")
})
control.onEvent(control.eventSourceId(EventBusSource.MICROBIT_ID_IO_P0),  control.eventValueId(EventBusValue.MICROBIT_PIN_EVT_FALL), () => {
    basic.showString("Fall")
})
pins.setEvents(DigitalPin.P0, PinEventType.Edge)
```

**고급 API 입니다.** 자세한 내용은 [@boardname@ runtime messageBus documentation](https://lancaster-university.github.io/microbit-docs/ubit/messageBus/) 를 살펴보세요.