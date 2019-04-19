# threshold

Get the distance threshold for when objects are near, far, or detected.

```sig
sensors.ultrasonic1.threshold(UltrasonicSensorEvent.ObjectDetected)
```

Whether something is near really depends on the situation. A object moving towards you is "near" at further distance than something that isn't moving due to the time necessary to move out of its way.

Distances for near have set *thresholds*. A threshold is a boundary or a limit. If near means anything that's closer that 20 centimeters, then the threshold for `near`.

Also, the threshold for nowing that something has moved within a distance from you is set for `detected`.

## 매개 변수

* **condition**: the condition to get the threshold distance for. These are: `near` and `detected`.

## 리턴값

* a [number](/types/number) that is the threshold distance in centimeters.

## 예시

When a near object is detected, show what the threshold is.

```blocks
sensors.ultrasonic4.onEvent(UltrasonicSensorEvent.ObjectNear, function () {
    brick.showValue("NearObjectThreshold", sensors.ultrasonic4.threshold(UltrasonicSensorEvent.ObjectNear), 1)
})
```

## 참고 항목

[set threshold](/reference/sensors/ultrasonic/set-threshold)