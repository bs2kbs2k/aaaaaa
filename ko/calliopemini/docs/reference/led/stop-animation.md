# LED 스크린 애니메이션 중지

재생중인 애니메이션과 대기 중인 애니메이션을 중지시킵니다.

```sig
led.stopAnimation()
```

### 예시

다음은 `LED 스크린 애니메이션 중지` 를 사용하는 코드 부분입니다. `B` 버튼을 누르면, 출력되는 문자열 애니메이션이 중단됩니다.

```blocks
input.onButtonPressed(Button.B, () => {
    led.stopAnimation();
});
basic.showString("STOP ME! STOP ME! PLEASE, WON'T SOMEBODY STOP ME?");
```

### ~hint

애니메이션을 출력하기 전에 `LED 스크린 애니메이션 중지` 를 먼저 설정해 놓는 것이 중요합니다. 그렇게 해야 `LED 스크린 애니메이션 중지` 부분이 실행되도록 미리 준비해 둘 수 있습니다.

### ~

### 참고 항목

[show animation](/reference/basic/show-animation)