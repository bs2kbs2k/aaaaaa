# 이벤트 생성

이벤트 신호를 발생시킵니다.

```sig
control.raiseEvent(control.eventSourceId(EventBusSource.MICROBIT_ID_BUTTON_A), control.eventValueId(EventBusValue.MICROBIT_EVT_ANY));
```

**고급 API 입니다.** 자세한 내용은 [@boardname@ runtime messageBus documentation](https://lancaster-university.github.io/microbit-docs/ubit/messageBus/) 를 살펴보세요.