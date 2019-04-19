# 연결 신호 강도 변하면 실행

연결된 장치와의 연결 신호 강도가 변했을 때 실행시킬 코드들을 등록할 수 있습니다.

## ~hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```sig
devices.onSignalStrengthChanged(() => {})
```

## 매개 변수

* `실행시킬 코드`: 연결된 장치와의 연결 신호 강도가 변했을 때 실행시킬 코드들.

## 예시

다음은 연결된 장치와의 연결 신호 강도를 출력하는 예시 코드입니다.:

```blocks
devices.onSignalStrengthChanged(() => {
    basic.showNumber(devices.signalStrength())
})
```

## 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [연결 신호 강도](/reference/devices/signal-strength)

```package
devices
```