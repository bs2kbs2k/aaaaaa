# 수형(Number)

An integer number.

### @parent blocks/language

A *Number* is an integer such as `42` or `-42`. More precisely, a *Number* is a signed 32-bit integer (two's complement).

### Declare a number variable

You can assign a number to a variable:

```blocks
let num = 42;
basic.showNumber(42);
```

### Arithmetic operators

The following arithmetic operators work on numbers and return a [Number](/reference/types/number):

* 더하기: `1 + 3`
* 빼기: `1 - 3`
* 곱하기: `3 * 2`
* 정수 나누기 (몫 계산): `7 / 3`
* 나머지(modulo) 계산은 [math](/blocks/math)라이브러리를 이용해 가능합니다.

### Relational operators

The following relational operators work on numbers and return a [Boolean](/blocks/logic/boolean):

* 같다: `(3 + 1) == 4`
* 다르다: `3 != 4`
* 작거나 같다: `3 <= 4`
* 작다: `3 < 4`
* 크거나 같다 : `4 >= 3`
* 크다: `4 > 3`

### Show number

[show number](/reference/basic/show-number)함수는 [LED 스크린](/device/screen)에 수를 출력합니다. 예를 들어, 다음 코드는 42 를 출력합니다.

```blocks
basic.showNumber(42);
```

### 수를 리턴하는 함수

함수에 따라서, 정수 변수에 정수 값을 저장해 리턴할 수 있습니다. 예를 들어, 다음 코드는 ([brightness function](/reference/led/brightness) 를 사용해) 디스플레이 밝기를 가져오고, `brightness` 변수에 그 값을 저장합니다.:

```blocks
let brightness = led.brightness()
```

### 계산 함수

[math](/blocks/math) 라이브러리에는 계산과 관련한 함수들이 포함되어있습니다. 예를 들어, `절댓값` 함수는 매개 변수 `x`에 저장되어있는 값의 절댓값을 리턴합니다.:

```blocks
let abs = Math.abs(-42);
basic.showNumber(abs);
```

### 참고 항목

[math](/blocks/math), [var](/blocks/variables/var), [Boolean](/blocks/logic/boolean), [show number](/reference/basic/show-number)