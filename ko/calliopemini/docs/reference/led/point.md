# LED 상태

[LED 스크린](/device/screen) 에 있는 특정 LED 가 켜져있는지 꺼져있는지 알아낼 수 있습니다.

```sig
led.point(0,0);
```

### 매개 변수

* `x` is a [number](/reference/types/number) that means the horizontal spot on the LED screen (from left to right: 0, 1, 2, 3, or 4)
* `y` is a [number](/reference/types/number) that means the vertical spot on the LED screen (from top to bottom: 0, 1, 2, 3, or 4)

매개 변수로 전달된 값이 [범위를 벗어나면](/reference/out-of-bounds) (0 부터 4 까지의 값이 아닌 경우), 불 값 `거짓(false)` 을 리턴합니다.

### 리턴값

* [불(참/거짓)](/blocks/logic/boolean). `참(true)` 인 경우 LED 가 켜져있다는 것을 의미합니다. `거짓(false)` 인 경우 LED 가 꺼져있다는 것을 의미합니다.

### ~hint

LED 스크린은, 여러 개의 LED 들을 정사각형(5*5) 모양으로 배치시킨 것입니다. `x`, `y` 좌표에 대해서 살펴보려면, [LED 스크린](/device/screen) 을 참고해주세요.

### ~

### 예시: LED 토글(반전)

다음은 스크린 가운데(2, 2)에 있는 LED 가 켜져있는 경우, 그 LED 를 끄는 예시입니다. (꺼져있던 경우에는, 꺼져있는 그 상태로 둡니다.)

```blocks
if (led.point(2, 2)) {
    led.unplot(2, 2)
}
```

### 참고 항목

[LED 끄기](/reference/led/unplot), [LED 켜기](/reference/led/plot), [LED 스크린](/device/screen)