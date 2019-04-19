# on IMU

Do something when then [9-Dof](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero 9-Dof") sensor detects a certain motion.

```sig
sensor.onIMU(IMUEvent.FreeFall, function () {
})
```

The 9-Dof sensor has an *inertial motion unit* (IMU) on it. This can detect several different kinds of motions. You pick the type of motion you want to run code for.

## 매개 변수

* **event**: the motion event you want to run some code for. The motions you can choose are: >`shake` , `tilt up`, `tilt down`, `tilt right`, `tilt left`, `face up`, `face down`, or `freefall`.
* **이벤트 핸들러**: IMU 이벤트가 발생했을 때 실행시킬 코드.

## 예시

Make the LED Matrix display a different icon for some of the motions that the 9-dof sensor can detect.

```blocks
sensor.onIMU(IMUEvent.FreeFall, function () {
    display.showIcon(IconType.Sad)
})
sensor.onIMU(IMUEvent.TiltUp, function () {
    display.showIcon(IconType.Up)
})
sensor.onIMU(IMUEvent.FaceUp, function () {
    display.showIcon(IconType.Yes)
})
```

## 참고 항목

[`||was imu triggered||`](/reference/sensor/was-imu-triggered) [`||acceleration||`](/reference/sensor/acceleration)