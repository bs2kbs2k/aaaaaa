# proximity Threshold

Get the proximity threshold for when objects are near and detected.

```sig
sensors.infrared1.proximityThreshold(InfraredSensorEvent.ObjectNear)
```

Infrared sensors determine proximity of an object by measuring the intensity of the infrared light reflected from it. The proximity range of measurment is from `0` to `100`. Proximity *thresholds* use a value in this range to decide when a proximity event should happen for a detected object.

## 매개 변수

* **condition**: the proximity threshold to return a value for. These are: `near` and `detected`.

## 리턴값

* a [number](/types/number) that is the proximity value for the threshold. This is a number between `0` and `100`.

## 예시

When an object with near proximity is detected, show what the threshold is.

```blocks
sensors.infrared1.onEvent(InfraredSensorEvent.ObjectNear, function () {
    brick.showValue("NearObjectThreshold", sensors.infrared1.proximityThreshold(InfraredSensorEvent.ObjectNear)
, 1)
})
```

## 참고 항목

[set proximity threshold](/reference/sensors/infrared/set-proximity-threshold)