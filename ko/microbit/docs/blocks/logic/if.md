# @extends

## #examples

## 예시: 스크린 밝기 조정

[빛 센서 밝기](/reference/input/light-level) 가 `< 100` 일 때, A 버튼을 누르면 스크린의 밝기를 `255` 로 변경합니다.:

```blocks
input.onButtonPressed(Button.A, () => {
    if(input.lightLevel()<100){
        led.setBrightness(255);
    }
})
```