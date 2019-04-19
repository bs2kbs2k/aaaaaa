# is IMU Event

Get the last [9-Dof](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero 9-Dof") sensor event that happened and check if it was a certain motion.

```sig
sensor.isIMUEvent(IMUEvent.FreeFall)
```

The 9-Dof sensor has an *inertial motion unit* (IMU) on it. This can detect several different kinds of motions. You pick the type of motion you want to check for.

## 매개 변수

* **event**: the motion event you want to check for. You choose one of these events: >`shake`, `tilt up`, `tilt down`, `tilt right`, `tilt left`, `face up`, `face down`, or `freefall`.

## 리턴값

* a [boolean](/types/boolean) value that is `true` if the event happened, or `false` if not.

## 예시

Make the LED Matrix show "I am dizzy" if the 9-Dof sensor detects a `shake`. If it detects a `freefall`, have the [Buzzer](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Buzzer") play a `High C` sound.

```blocks
loops.forever(function () {
    if (sensor.isIMUEvent(IMUEvent.FreeFall)) {
        sound.ringTone(523)
    } else if (sensor.isIMUEvent(IMUEvent.Shake)) {
        display.showString("I am dizzy")
    }
})
```

## 참고 항목

[`||on imu||`](/reference/sensor/on-imu) [`||acceleration||`](/reference/sensor/acceleration)