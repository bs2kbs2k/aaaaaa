# 백그라운드로 실행

다른 작업을 실행하는 동안, 동시에 프로그램 코드를 실행시킵니다.

```sig
control.inBackground(() => {
})
```

### ~hint

더 자세한 내용은, [@boardname@ - 반응 시스템](/device/reactive) 자료를 살펴보세요. 전문가용 고급자료입니다!

### ~

### 예시

다음은 `num` 과 같은 변수에 저장된 값을 백그라운드로 보여주는 코드입니다. 다른 코드 부분(`버튼 누르면 실행`)은 계속해서 변수에 저장되어있는 값을 갱신합니다.

```blocks
let num = 0
control.inBackground(() => {
    while (true) {
        basic.showNumber(num, 150)
        basic.pause(100)
    }
})
input.onButtonPressed(Button.A, () => {
    num++;
})
```

다음은 같은 동작을 하는 코드이지만, `무한 반복 실행` 구조를 이용하는 일반적인 예시입니다.

```blocks
let num = 0
basic.forever(() => {
    basic.showNumber(num, 150)
})
input.onButtonPressed(Button.A, () => {
    num++;
})
```

### 참고 항목

[반복(while)](/blocks/loops/while), [무한 반복 실행](/reference/basic/forever), [버튼 누르면 실행](/reference/input/on-button-pressed)