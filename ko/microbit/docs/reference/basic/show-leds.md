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

## 매개 변수

* `LED 상태`. 켜고 끌 LED 상태는 그 상태를 표현하는 [문자열](/types/string)이라고 할 수 있습니다.
* `갱신 주기`(옵션). 다음 그림 상태로 바꿀 때까지 기다리는 시간 간격을 의미하는 값 [수(정수)](/types/number). 블록을 사용해 프로그래밍하는 경우, `갱신 주기`는 400 밀리 초로 설정됩니다.

## 예시

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

## ~hint

자바스크립트를 이용해 프로그래밍하는 경우, `#` 는 LED on, `.` 는 LED off 를 의미합니다.

## ~

## 참고 항목

[LED 켜기](/reference/basic/plot-leds), [애니메이션 출력](/reference/basic/show-animation)