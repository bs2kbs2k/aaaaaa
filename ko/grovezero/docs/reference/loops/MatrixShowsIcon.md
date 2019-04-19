# MatrixShowsIcon

LED 매트릭스에 아이콘이나 픽셀 이미지를 출력합니다.

```sig
display.showIcon(IconType.Smile)

```

When code in `||MatrixShowsIcon||`, it will display an icon or pixel image on LED matrix.

## 매개 변수

* **icon**: *heart*, *small heart*, *yes* , *no*, *grove zero* etc.

## 예시

LED matrix displays smile face when it is light, diplays sad face when it is dark.

```blocks
sensor.onLight(LightEvent.Light, function () {
    display.showIcon(IconType.Smile)
})
sensor.onLight(LightEvent.Dark, function () {
    display.showIcon(IconType.Sad)
})


```

## 참고 항목

[`||MatrixShowsNumber||`](/reference/display/MatrixShowsNumber) [`||MatrixShowsString||`](/reference/display/MatrixShowsString)