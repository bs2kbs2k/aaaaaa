# 디스플레이 모드 설정

[LED](/device/screen) 렌더링 모드를 흑백/그레이스케일 모드로 설정합니다.

```sig
led.setDisplayMode(DisplayMode.Greyscale)
```

디스플레이 모드 설정을 이용해, LED 스크린의 컬러 출력 가능 범위를 설정할 수 있습니다. 컬러 출력 범위(color depth) 는, 표현할 수 있는 픽셀의 색 가짓수를 의미합니다. `그레이스케일(greyscale)` 모드를 사용하면, 픽셀의 색을 회색 스케일의 빛 밝기로 바꿔 출력할 수 있습니다. `흑백(black and white)` 모드를 사용하면, 이미지 픽셀의 색을 켜거나 끄는 2 가지 생태로만 바꿔 출력할 수 있습니다.

## 매개 변수

* `모드(mode)`. 디스플레이 모드 타입. `BlackAndWhite` 나 `GreyScale` 중 한 가지로 설정할 수 있습니다.

## 예시

다음은 디스플레이 모드를 `흑백(black and white)` 모드로 설정하는 예시입니다.

```blocks
led.setDisplayMode(DisplayMode.BackAndWhite)
```

## 참고 항목

[set brightness](/reference/led/set-brightness)