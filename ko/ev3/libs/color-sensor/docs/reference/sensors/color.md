# color

Get a color that the sensor can detect that is close to the color you asked for.

```sig
sensors.color(ColorSensorColor.Blue)
```

Since the color sensor can accurately detect some basic colors, you can't just tell it to look for any color. The sensor may recoginze some color component of the color you ask for. So, you can get a simple color that matches some of your color and tell the sensor to look for that.

## 매개 변수

* **color**: a color to match with a detectable color. The colors to choose from are:

> * `파란색`
> * `녹색 `
> * `노란색`
> * `빨간색`
> * `흰색`
> * `갈색`

## 리턴값

* a color value that the color sensor can detect. The detectable colors are:

> * `파란색`
> * `녹색 `
> * `노란색`
> * `빨간색`
> * `흰색`
> * `갈색`

## ~hint

Currently, the colors you can ask for (input colors) and the colors returned are the same.

## ~

## 예시

Turn the status light to `green` if the color detected by the `color 1` sensor is green.

```blocks
forever(function () {
    if (sensors.color1.color() == sensors.color(ColorSensorColor.Green)) {
        brick.setStatusLight(StatusLight.Green)
    } else {
        brick.setStatusLight(StatusLight.Orange)
    }
})
```

## 참고 항목

[color](/reference/sensors/color-sensor/color)