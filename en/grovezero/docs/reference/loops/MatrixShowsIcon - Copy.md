# MatrixShowsIcon

Display an icon or pixel image on LED matrix.

```sig
display.showIcon(IconType.Smile)

```

When code in `||MatrixShowsIcon||`, it will display an icon or pixel image on LED matrix.

## Parameters

* **icon**: *heart*, *small heart*, *yes* , *no*, *grove zero* etc.

## Example

LED matrix displays smile face when it is light, diplays sad face when it is dark.

```blocks
sensor.onLight(LightEvent.Light, function () {
    display.showIcon(IconType.Smile)
})
sensor.onLight(LightEvent.Dark, function () {
    display.showIcon(IconType.Sad)
})


```

## See also

[`||MatrixShowsNumber||`](/reference/display/MatrixShowsNumber) [`||MatrixShowsString||`](/reference/display/MatrixShowsString)