# 재설정/초기화

@boardname@ 의 전원을 리셋하고, 프로그램을 다시 시작시킵니다.

이 함수는 @boardname@ 뒷면에 있는 리셋 버튼을 누른 것과 같은 효과를 만들어냅니다.

```sig
control.reset()
```

## ~hint

**시뮬레이터**

The **reset** function works only on a real @boardname@ and not in the simulator.

## ~

## 예시

다음은 `A` 버튼을 누를 때마다 카운트를 올리는 프로그램입니다. `B` 버튼을 누르면 @boardname@ 가 재시작되고 프로그램이 다시 시작됩니다.

```blocks
let item = 0;
basic.showNumber(item);
input.onButtonPressed(Button.A, () => {
    item = item + 1;
    basic.showNumber(item);
});
input.onButtonPressed(Button.B, () => {
    control.reset();
});
```

## 참고 항목

[LED 스크린 지우기](/reference/basic/clear-screen), [게임 종료](/reference/game/game-over)