# 버튼 눌림 상태

현재 어떤 버튼이 눌려있는지 확인할 수 있습니다. @boardname@ 에는 2개의 버튼이 있습니다.: `A` 버튼과 `B` 버튼이 있습니다.

```sig
input.buttonIsPressed(Button.A);
```

### 매개 변수

* `button` is a [String](/reference/types/string). 왼쪽 버튼의 눌림을 확인하려면 `A`, 오른쪽 버튼의 눌림을 확인하려면 `B`, 두 버튼이 모두 눌린 것을 확인하려면 `A+B` 를 선택하면 됩니다.

### 리턴값

* [불(참/거짓)](/blocks/logic/boolean). 그 버튼이 눌린 경우 `참(true)`, 안 눌린 경우 `거짓(false)`.

### 예시

다음 코드는 [만약(if)](/blocks/logic/if) 구조를 이용해서 `A` 버튼의 눌림을 확인하고, 그에 따라 다른 코드를 실행시키는 예시입니다.

```blocks
basic.forever(() => {
    let pressed = input.buttonIsPressed(Button.A)
    if (pressed) {
        // this part runs if the A button is pressed
        basic.showNumber(1, 150)
    } else {
        // this part runs if the A button is *not* pressed
        basic.showNumber(0, 150)
    }
})
```

### 참고 항목

[버튼 누르면 실행](/reference/input/on-button-pressed) [만약(if)](/blocks/logic/if), [무한 반복 실행](/reference/basic/forever)