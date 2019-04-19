# 수형(Number)

An integer number.

### @parent blocks/language

A *Number* is an integer such as `42` or `-42`. More precisely, a *Number* is a signed 32-bit integer (two's complement).

### Declare a number variable

You can assign a number to a variable:

#### #declareexample

```block
let num = 42;
```

### Arithmetic operators

The following arithmetic operators work on numbers and return a [Number](/types/number):

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

## #print

### 수를 리턴하는 함수

함수에 따라서, 정수 변수에 정수 값을 저장해 리턴할 수 있습니다.

### #functionreturnexample

```block
let abs = Math.abs(-42);
```

### 계산 함수

The [math library](/blocks/math) includes math related functions. For example, the `min` function returns the minimum value of two input parameters `x` and `y`:

```block
let lowest = Math.min(-42, 1000);
```

### 참고 항목

[계산](/blocks/math), [변수](/blocks/variables/var), [불(참/거짓)](/blocks/logic/boolean)