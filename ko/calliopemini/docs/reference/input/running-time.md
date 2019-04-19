# 전원 켜진 후 흐른 시간(ms)

Find how long it has been since the program started.

```sig
input.runningTime();
```

### 리턴값

* the [Number](/reference/types/number) of milliseconds since the program started. (One second is 1000 milliseconds.)

### 예시: 실행 후 흐른 시간

마이크로비트의 `B` 버튼을 누르면, 프로그램이 실행 된 후 흐른 시간을 알아내 [LED 스크린](/device/screen) 화면에 출력해줍니다.

```blocks
input.onButtonPressed(Button.B, () => {
    let now = input.runningTime()
    basic.showNumber(now)
})
```

### 참고 항목

[정수 출력](/reference/basic/show-number), [일시 중지](/reference/basic/pause)