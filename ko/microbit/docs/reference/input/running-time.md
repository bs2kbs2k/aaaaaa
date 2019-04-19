# 전원 켜진 후 흐른 시간(ms)

프로그램이 실행 된 후 흐른 시간을 밀리초 단위로 알아낼 수 있습니다.

```sig
input.runningTime();
```

## 리턴값

* [정수](/types/number). 프로그램이 실행 된 후 흐른 시간(밀리초). (1 초는 1000 밀리초)

## 예시: 실행 후 흐른 시간

마이크로비트의 `B` 버튼을 누르면, 프로그램이 실행 된 후 흐른 시간을 알아내 [LED 스크린](/device/screen) 화면에 출력해줍니다.

```blocks
input.onButtonPressed(Button.B, () => {
    let now = input.runningTime()
    basic.showNumber(now)
})
```

## 참고 항목

[정수 출력](/reference/basic/show-number), [일시 중지](/reference/basic/pause)