# LED 반전

[LED 스크린](/device/screen) 의 모든 LED 상태를 반전시킵니다. 켜져(on)있던 것은 꺼지고(off), 꺼져있던 것은 켜지게 됩니다. x, y 좌표 체계를 사용합니다.

```sig
led.toggle(0,0)
```

## 매개 변수

* x - [수(정수)](/types/number). *x좌표*. 오른쪽 방향 위치 (0, 1, 2, 3, 4)
* y - [수(정수)](/types/number). *y좌표*. 오른쪽 방향 위치 (0, 1, 2, 3, 4)

매개 변수로 전달된 값이 [범위를 벗어나면](/reference/out-of-bounds) (0 부터 4 까지의 값이 아닌 경우), 아무 동작도 실행되지 않습니다.

## x, y 좌표란?

LED 스크린은 25 개의 LED 가 5x5 격자 형태로 배치되어 있습니다. `x`, `y` 좌표 체계에 대해서 더 자세히 살펴보려면, [LED 스크린](/device/screen) 을 살펴보세요.

## 예시

다음은 가운데에 있는 LED 상태를 반전시키는 예시 코드입니다.

```blocks
led.toggle(2, 2)
```

## 참고 항목

[LED 전체 반전](/reference/led/toggle-all), [LED 켜기](/reference/led/plot), [LED 끄기](/reference/led/unplot), [LED 상태](/reference/led/point), [LED 스크린](/device/screen),