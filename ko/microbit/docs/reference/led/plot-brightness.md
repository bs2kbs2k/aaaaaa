# LED 켜기

[LED 스크린](/device/screen) 의 특정 LED 불빛을 켭니다.

```sig
led.plotBrightness(0,0, 128);
```

### 매개 변수

* `x좌표`. [수(정수)](/types/number). LED 스크린에서 오른쪽 방향으로의 위치를 의미합니다. (왼쪽에서 오른쪽으로 가면서: 0, 1, 2, 3, 4)
* `y좌표`. [수(정수)](/types/number). LED 스크린에서 아래쪽 방향으로의 위치를 의미합니다. (위에서 아래쪽으로 가면서: 0, 1, 2, 3, 4)
* ``밝기`. [수(정수)](/types/number). LED 의 밝기를 의미합니다. 0 (끔) 부터 255 (가장 밝음) 까지의 범위를 사용할 수 있습니다.

매개 변수로 전달된 값이 [범위를 벗어나면](/reference/out-of-bounds) (0 부터 4 까지의 값이 아닌 경우), 아무 동작도 실행되지 않습니다.

### ~hint

LED 스크린은, 여러 개의 LED 들을 정사각형(5*5) 모양으로 배치시킨 것입니다. `x`, `y` 좌표에 대해서 살펴보려면, [LED 스크린](/device/screen) 을 참고해주세요.

### ~

### 예시: LED 1개 켜기

다음은 오른쪽 아래에 있는 LED 를 50% 밝기로 켜는 예시입니다.

```blocks
led.plotBrightness(2, 2, 128)
```

### 예시: 사각형 만들기

다음은 [반복(for)](/blocks/loops/for) 구조와 `LED 켜기` 함수를 사용해, 스크린의 가장 바깥쪽 LED 들을 사각형 모양으로 켜는 예시입니다.

```blocks
for (let i = 0; i < 5; i++) {
    led.plotBrightness(0, i, 64)
    led.plotBrightness(4, i, 128)
    led.plotBrightness(i, 0, 172)
    led.plotBrightness(i, 4, 255)
    basic.pause(500)
}
```

### ~hint

어떤 LED 의 on/off 상태를 확인하려면, [LED 상태](/reference/led/point) 함수를 사용하면 됩니다.

### ~

### 참고 항목

[LED 켜기](/reference/led/plot), [LED 끄기](/reference/led/unplot), [LED 상태](/reference/led/point), [LED 스크린](/device/screen)