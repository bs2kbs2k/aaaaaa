# @extends

## 정수 출력 #print

[show number](/reference/basic/show-number)함수는 [LED 스크린](/device/screen)에 수를 출력합니다. 예를 들어, 다음 코드는 42 를 출력합니다.

```block
basic.showNumber(42);
```

### #declareexample

```block
let num = 42;
basic.showNumber(42);
```

### #functionreturnexample

예를 들어, 다음 코드는 ([brightness function](/reference/led/brightness) 를 사용해) 디스플레이 밝기를 가져오고, `brightness` 변수에 그 값을 저장합니다.:

```block
let brightness = led.brightness()
```