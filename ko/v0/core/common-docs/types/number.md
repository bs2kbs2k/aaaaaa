# 수형(Number)

정수(integer)를 의미합니다.

## @parent blocks/language

A *Number* is an integer such as `42` or `-42`. More precisely, a *Number* is a signed 32-bit integer (an integer value that contains a positive or negative sign as part of it's information).

## Declare a number variable

변수에 정수 값을 저장할 수 있습니다.

### #declareexample

```block
let num = 42;
```

## Arithmetic operators

다음과 같은 산술 연산자들은 정수들 사이에서 사용되며, 그 계산 결과도 [정수](/types/number) 값으로 리턴합니다.:

* 더하기: `1 + 3`
* 빼기: `1 - 3`
* 곱하기: `3 * 2`
* 정수 나누기 (몫 계산): `7 / 3`
* 나머지(modulo) 계산은 [math](/blocks/math)라이브러리를 이용해 가능합니다.

## Relational operators

다음과 같은 조건/관계 연산자들은 정수들 사이에서 사용되며, 그 계산 결과는 [불형(Boolean)](/blocks/logic/boolean) 참(true) 또는 거짓(false)으로 리턴합니다.:

* 같다: `(3 + 1) == 4`
* 다르다: `3 != 4`
* 작거나 같다: `3 <= 4`
* 작다: `3 < 4`
* 크거나 같다 : `4 >= 3`
* 크다: `4 > 3`

## #print

## 수를 리턴하는 함수

함수에 따라서, 정수 변수에 정수 값을 저장해 리턴할 수 있습니다.

### #functionreturnexample

```block
let abs = Math.abs(-42);
```

## 계산 함수

[math](/blocks/math) 라이브러리에는 계산과 관련한 함수들이 포함되어있습니다. 예를 들어, `절댓값` 함수는 매개 변수 `x`에 저장되어있는 값의 절댓값을 리턴합니다.:

```block
let abs = Math.min(-42, 1000);
```

## 참고 항목

[계산](/blocks/math), [변수](/blocks/variables/var), [불(참/거짓)](/blocks/logic/boolean)