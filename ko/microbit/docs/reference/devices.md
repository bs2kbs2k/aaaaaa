# 장치제어

@boardname@ 의 블루투스 기능을 이용해 스마트폰을 제어합니다.

## ~ hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```cards
devices.tellCameraTo(MesCameraEvent.TakePhoto);
devices.tellRemoteControlTo(MesRemoteControlEvent.play);
devices.raiseAlertTo(MesAlertEvent.DisplayToast);
devices.onNotified(MesDeviceInfo.IncomingCall, () => {

});
devices.onGamepadButton(MesDpadButtonInfo.ADown, () => {

});
devices.signalStrength();
devices.onSignalStrengthChanged(() => {

});
```

```package
devices
```

## 참고 항목

[카메라 동작 명령 전송](/reference/devices/tell-camera-to), [리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to), [장치제어 감지하면 실행](/reference/devices/on-notified), [게임패드 감지하면 실행](/reference/devices/on-gamepad-button), [연결 신호 강도](/reference/devices/signal-strength), [연결 신호 강도 변하면 실행](/reference/devices/on-signal-strength-changed)