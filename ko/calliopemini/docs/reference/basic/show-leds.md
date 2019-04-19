# LED 출력

[LED 스크린](/device/screen)에 원하는 모양을 그려 출력합니다.

```sig
basic.showLeds(`
    . . . . .
    . # . # .
    . . # . .
    # . . . #
    . # # # .
    `
)
```

### 매개 변수

* `leds` is a [string](/reference/types/string) that controls which LEDs are on and off.
* `interval` is an optional [number](/reference/types/number) that means how many milliseconds to wait after showing a picture. 블록을 사용해 프로그래밍하는 경우, `갱신 주기`는 400 밀리 초로 설정됩니다.

### 예시

아래 프로그램은 `LED 출력` 함수를 이용해 그림을 출력합니다.

```blocks
basic.showLeds(`
    # # . # #
    # # . # #
    . # # # .
    . # . # .
    . # . # .
    `
)
```

### ~hint

자바스크립트를 이용해 프로그래밍하는 경우, `#` 는 LED on, `.` 는 LED off 를 의미합니다.

### ~

### 참고 항목

[plot leds](/reference/led/plot-leds), [show animation](/reference/basic/show-animation)