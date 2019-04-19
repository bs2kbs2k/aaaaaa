# acceleration

Get the acceleration value in milli-gravities (mg) in the X, Y, or Z direction.

```sig
sensor.acceleration(Axis.X)

```

## Parameters

* **axis**: the direction (axis) of acceleration you want to measure. This is either `X`, `Y`, or `Z`.

## Returns

* a [number](/types/number) that is the acceleration value in the direction asked for in **axis**.

## Example

Check the acceleration value for the X axis from the 9-Dof sensor every 1 seconds. Show the value on the LED Matrix.

```blocks
loops.forever(function () {
    display.showNumber(sensor.acceleration(Axis.X))
    loops.pause(1000);
})
```

## See also

[`||was imu triggered||`](/reference/sensor/was-imu-triggered) [`||on imu||`](/reference/sensor/on-imu)