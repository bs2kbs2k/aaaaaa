# 버튼 누르면 실행

[이벤트 핸들러](/reference/event-handler)(어떤 버튼이 눌린 것과 같은 이벤트가 발생했을 때, 실행되는 작은 프로그램)를 실행합니다. 이 이벤트 핸들러는 `A` 버튼, `B` 버튼, `A` 버튼과 `B` 버튼이 함께 눌린 경우 실행됩니다. 이 함수를 웹브라우저의 편집기에서 사용하는 경우, @boardname@ 의 버튼을 직접누르는 대신에 시뮬레이터 화면에 있는 버튼을 누르면 됩니다.

* `A` 버튼 또는 `B` 버튼: 이 이벤트 핸들러는 버튼을 누른 후 1초 이내에 놓았을 때 실행됩니다.
* `A` 버튼과 `B` 버튼을 함께: 이 이벤트 핸들러는 `A` 버튼과 `B` 버튼을 함께 눌렸다가 1.5 초 이내에 둘 중 하나를 놓았을 때 실행됩니다.

```sig
input.onButtonPressed(Button.A, () => {})
```

## 예시: 버튼 클릭 카운터

다음 코드는 `A` 버튼을 누른 횟수를 카운트합니다. 버튼을 누를 때마다 카운트 횟수가 증가되고, [LED 스크린](/device/screen) 에 `count` 변수에 저장된 값이 출력됩니다.

```blocks
let count = 0
basic.showNumber(count)
input.onButtonPressed(Button.A, () => {
    count++;
    basic.showNumber(count);
})
```

## 예시: 주사위 던지기

다음 코드는 `B` 버튼을 누를 때마다, 1 부터 6 까지 범위의 정수 중에서 랜덤으로 뽑아 출력해 보여줍니다.

```blocks
input.onButtonPressed(Button.B, () => {
    let dice = Math.random(6) + 1
    basic.showNumber(dice)
})
```

## ~hint

이 코드는 `random(6)` 로 얻어진 랜덤 값(0 ~ 5)에 `1` 을 더해서 화면에 출력합니다. 마치 주사위를 1개 던진 것과 같은 형태로 동작합니다. 만약, 1을 더하지 않으면 `0`부터 5 까지 출력되게 됩니다.

## ~

## 참고 항목

[버튼 눌림 상태](/reference/input/button-is-pressed), [무한 반복 실행](/reference/basic/forever), [랜덤 선택](/blocks/math)