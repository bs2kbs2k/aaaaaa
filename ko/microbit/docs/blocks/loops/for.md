# @extends

## #examples

## 예시: 4까지 카운트하기

다음 코드는 0, 1, 2, 3, 4 를 한 번에 하나씩 LED 스크린에 출력할 것입니다.

```blocks
input.onButtonPressed(Button.A, () => {
    for(let i = 0; i < 5; ++i) {
        basic.showNumber(i)
    }
})
```