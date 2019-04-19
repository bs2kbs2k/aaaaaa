# LED 끄기

[LED 스크린](/device/screen) 의 특정 LED 불빛을 끕니다.

```sig
led.unplot(0,0)
```

## ~hint

[LED 켜기](/reference/led/plot) 를 사용하면, 원하는 위치에 있는 LED 를 **on** 시킬 수 있습니다.

## ~

## 매개 변수

* `x좌표`. [수(정수)](/types/number). LED 스크린에서 오른쪽 방향으로의 위치를 의미합니다. (왼쪽에서 오른쪽으로 가면서: 0, 1, 2, 3, 4)
* `y좌표`. [수(정수)](/types/number). LED 스크린에서 아래쪽 방향으로의 위치를 의미합니다. (위에서 아래쪽으로 가면서: 0, 1, 2, 3, 4)

매개 변수로 전달된 값이 [범위를 벗어나면](/reference/out-of-bounds) (0 부터 4 까지의 값이 아닌 경우), 아무 동작도 실행되지 않습니다.

## ~hint

LED 스크린은, 여러 개의 LED 들을 정사각형(5*5) 모양으로 배치시킨 것입니다. `x`, `y` 좌표에 대해서 살펴보려면, [LED 스크린](/device/screen) 을 참고해주세요.

## ~

## 예시: 가운데 끄기

다음은 LED 스크린에 이미지를 출력한 후, `LED 끄기` 를 사용해 가운데 LED 를 끕니다.

```blocks
basic.showLeds(`
. . # . .
. . # . .
# # # # #
. . # . .
. . # . .
`)
basic.pause(500)
led.unplot(2, 2)
```

## ~hint

어떤 LED 의 on/off 상태를 확인하려면, [LED 상태](/reference/led/point) 함수를 사용하면 됩니다.

## ~

## 참고 항목

[LED 켜기](/reference/led/plot), [LED 상태](/reference/led/point), [LED 스크린](/device/screen)