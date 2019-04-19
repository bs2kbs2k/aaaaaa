# 고급제어

실행중/이벤트 유틸리티

```cards
control.inBackground(() => {

});
control.reset();
control.waitMicros(4);
control.onEvent(0, 0, () => { });
control.raiseEvent(0, 0);
control.eventTimestamp();
control.eventValue();
```

## 참고 항목

[백그라운드로 실행](/reference/control/in-background), [마이크로비트 재부팅(reset)](/reference/control/reset), [상태 유지(µs)](/reference/control/wait-micros), [이벤트 발생시 실행](/reference/control/on-event), [이벤트 생성](/reference/control/raise-event), [이벤트 타임스탬프](/reference/control/event-timestamp), [이벤트 값](/reference/control/event-value)