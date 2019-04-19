# 연결 신호 강도

연결된 장치와의 연결 신호 강도를 알아낼 수 있습니다. 신호 강도는 `0` (신호 없음) 부터 `4` (가장 강함) 까지 범위의 값으로 리턴됩니다.

## ~hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```sig
devices.signalStrength();
```

## 리턴값

* 연결 신호 강도. `0` (신호 없음) 부터 `4` (가장 강함) 까지 범위의 값.

## 예시

다음은 연결된 장치와의 연결 신호 강도를 출력하는 예시 코드입니다.:

```blocks
devices.onSignalStrengthChanged(() => {
    basic.showNumber(devices.signalStrength())
})
```

## 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [연결 신호 강도 변하면 실행](/reference/devices/on-signal-strength-changed)

```package
devices
```