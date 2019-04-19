# 입력

센서들로부터 전송된 이벤트와 데이터

```cards
input.onButtonPressed(Button.A, () => {

});
input.onGesture(Gesture.Shake, () => {

});
input.onPinPressed(TouchPin.P0, () => {

});
input.buttonIsPressed(Button.A);
input.compassHeading();
input.pinIsPressed(TouchPin.P0);
input.temperature();
input.acceleration(Dimension.X);
input.lightLevel();
input.rotation(Rotation.Pitch);
input.magneticForce(Dimension.X);
input.runningTime();
input.runningTimeMicros();
input.setAccelerometerRange(AcceleratorRange.OneG);
```

## 참고 항목

[버튼 누르면 실행](/reference/input/on-button-pressed), [동작 감지하면 실행](/reference/input/on-gesture), [핀 연결되면 실행](/reference/input/on-pin-pressed), [버튼 눌림 상태](/reference/input/button-is-pressed), [자기(나침반) 센서 각도](/reference/input/compass-heading), [핀 연결(on) 상태](/reference/input/pin-is-pressed), [온도 센서 온도](/reference/input/temperature), [가속도 센서 가속도](/reference/input/acceleration), [LED 스크린 빛 센서 밝기](/reference/input/light-level), [기울기 센서 각도](/reference/input/rotation), [자기(나침반) 센서 자기력](/reference/input/magnetic-force), [전원 켜진 후 흐른 시간(ms)](/reference/input/running-time), [가속도 센서 감지 값 설정](/reference/input/set-accelerometer-range), [자기(나침반) 센서 보정](/reference/input/calibrate-compass)