# @extends

## #examples

## 예시: 대각선 출력하기

다음은 while 반복 구조를 이용해 LED 화면에 대각선(점 찍기 `0, 0`, `1, 1`, `2, 2`, `3, 3`, `4, 4`)을 출력하는 예시입니다.

```blocks
input.onButtonPressed(Button.A, () => {
    let index = 4;
    while(index >= 0) {
        led.plot(index, index);
        index--;
    }
})
```