# @extends

## #exstart

다음은 프로그램이 `실행` 된 후, 버튼을 눌렀을 때, LED 스크린에 문자열을 출력하고 화면의 밝기를 설정하는 예시입니다.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString("Hello!")
})
led.setBrightness(50)
```