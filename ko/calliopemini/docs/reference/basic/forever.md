# 무한 반복 실행

어떤 프로그램을 반복 실행시킵니다. [백그라운드에서](/reference/control/in-background).

```sig
basic.forever(() => {
})
```

### 예시: 나침반

다음의 예시는 계속 반복해서 [자기장 방향](/reference/input/compass-heading)을 체크하고, 그 방향을 스크린 화면에 업데이트하며 보여줍니다.

```blocks
basic.forever(() => {
    let heading = input.compassHeading()
    if (heading < 45) {
        basic.showString("N", 100)
    } else if (heading < 135) {
        basic.showString("E", 100)
    }
    else if (heading < 225) {
        basic.showString("S", 100)
    }
    else {
        basic.showString("W", 100)
    }
})
```

### 예시: 카운터

The following example keeps showing the [number](/reference/types/number) stored in a global variable. `A` 버튼을 누르면, 수(값)가 커집니다. 어떤 횟수 등을 세거나 저장시키기 위해서 다음과 같은 코드를 @boardname@에서 사용할 수 있습니다.

```blocks
let num = 0
basic.forever(() => {
    basic.showNumber(num, 150)
})
input.onButtonPressed(Button.A, () => {
    num = num + 1
})
```

### LED 스크린 선점

동시에 LED 스크린을 사용해 표시하려는 서로 다른 프로그램이 있을 경우, 예상하지 못한 결과가 나타날 수 있습니다. @boardname@ 에서 다음 코드를 실행시켜보세요.:

```blocks
basic.forever(() => {
    basic.showNumber(6789, 150)
})
input.onButtonPressed(Button.A, () => {
    basic.showNumber(2, 150)
})
```

### 참고 항목

[반복(while)](/blocks/loops/while), [버튼 누르면 실행](/reference/input/on-button-pressed), [백그라운드 실행](/reference/control/in-background)