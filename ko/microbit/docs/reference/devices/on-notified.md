# On Notified

Register code to run when the signal strength of the paired device changes.

## ~hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```sig
devices.onNotified(MesDeviceInfo.IncomingCall, () => {})
```

## 매개 변수

* `body`: code to run when the signal strength changes.

## 예시

다음은 연결된 장치와의 연결 신호 강도를 출력하는 예시 코드입니다.:

```blocks
devices.onNotified(MesDeviceInfo.IncomingCall, () => {
    basic.showString("RING RING")
})
```

## 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [연결 신호 강도](/reference/devices/signal-strength)

```package
devices
```