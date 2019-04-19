# @extends

### #letexample

[brightness ](/reference/led/brightness) 함수를 통해 리턴된 값을 저장하는 변수를 만드는 방법은 다음과 같습니다.

```block
let b = led.brightness();
```

### #readvariableexample

예를 들어, 다음 코드에서는 `counter` 변수에 저장되어있는 값을 LED 스크린으로 출력해줍니다:

```blocks
let counter = 1;
basic.showNumber(counter);
```

### #updatevariableexample

다음 코드는 `counter` 를 1로 설정한 다음 `counter` 를 10 만큼씩 증가시킵니다.

```block
let counter = 1;
counter = counter + 10;
basic.showNumber(counter);
```

### #whyusevariablesexample

카운터는 아주 좋은 예시입니다.:

```block
let counter = 0;
input.onButtonPressed(Button.A, () => { 
  counter = counter + 1;
  basic.showNumber(counter);
});
```

### #localvariableexample

```block
// x does NOT exist here.
if (led.brightness() > 128) {
  // x exists here
  let x = 0;
}
```