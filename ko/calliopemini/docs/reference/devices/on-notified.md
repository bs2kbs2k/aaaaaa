# 연결 신호 강도 변하면 실행

연결된 장치와의 연결 신호 강도가 변했을 때 실행시킬 코드들을 등록할 수 있습니다.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
devices.onNotified(MesDeviceInfo.IncomingCall, () => {})
```

### 매개 변수

* `실행시킬 코드`: 연결된 장치와의 연결 신호 강도가 변했을 때 실행시킬 코드들.

### 예시

다음은 연결된 장치와의 연결 신호 강도를 출력하는 예시 코드입니다.:

```blocks
devices.onNotified(MesDeviceInfo.IncomingCall, () => {
    basic.showString("RING RING")
})
```

### 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [연결 신호 강도](/reference/devices/signal-strength)

```package
장치제어
```