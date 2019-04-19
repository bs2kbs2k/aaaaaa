# 게임 패드 버튼 감지하면 실행

페어링된 게임패드에서 @boardname@ 로 명령이 전송되면, 설정한 작업을 실행합니다.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
devices.onGamepadButton(MesDpadButtonInfo.ADown, () => {})
```

### 매개 변수

* `실행시킬 코드`: 게임패드에서 @boardname@ 로 명령이 전송되었을 때 실행시킬 코드.

### 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [연결 신호 강도](/reference/devices/signal-strength), [연결 신호 강도 변하면 실행](/reference/devices/on-signal-strength-changed)

```package
장치제어
```