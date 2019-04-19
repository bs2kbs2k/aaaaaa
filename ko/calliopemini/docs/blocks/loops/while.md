# While

Repeat code while a [Boolean](/blocks/logic/boolean) `condition` is true.

```blocks
while(true) {
}
```

The while loop has a *condition* that evaluates to a [Boolean](/blocks/logic/boolean) value. After the `do` keyword, add the code that you want to run while the `condition` is `true`. The while loop concludes with `end while`.

The condition is tested before any code runs. Which means that if the condition is false, the code inside the loop doesn't execute.

### 예시: 대각선 출력하기

다음은 while 반복 구조를 이용해 LED 화면에 대각선(점 찍기 `0, 0`, `1, 1`, `2, 2`, `3, 3`, `4, 4`)을 출력하는 예시입니다.

```blocks
let index = 4;
while(index >= 0) {
    led.plot(index, index);
    index--;
}
```

### 참고 항목

[on button pressed](/reference/input/on-button-pressed), [for](/blocks/loops/for), [if](/blocks/logic/if), [forever](/reference/basic/forever)