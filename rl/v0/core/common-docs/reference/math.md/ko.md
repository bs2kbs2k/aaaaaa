# 계산

[수(정수)](/types/number), 산술 연산자, 계산 함수 사용하기

## 수(정수) 값: 0, 1, 2...

수(값) 그 자체를 의미합니다. 때때로, *수 리터럴(literals)*이라고 부르기도 합니다.

### 정수: 소수부분(fraction)이 없는 수

```block
let num = 0;
num = 0;
num = 1;
num = 2;
```

## 산술 연산 (+, -, *, /)

기본적인 산술 연산: 더하기, 빼기, 곱하기, 나누기.

```block
let more = 0+1;
let less = 0-1;
let twice = 1*2;
let divide = 8/4;
```

### 나머지 연산 (%)

나머지 연산은, 나누기 연산과 관련된 추가 연산입니다. 어떤 수를 다른 수로 나누었을 때, 나누어떨어지지 않고 남는 값이 있습니다.

4 / 2 = 2 이기 때문에, 4 는 2 두개로 똑같이 나누어떨어집니다. 하지만, 5 / 2 = 2 ... 1(나머지) 이 됩니다. 이것을 나머지 연산으로 표현하면 5 % 2 = 1 이 됩니다. 나머지 연산은 나눈 나머지를 계산하는 것입니다.

```block
let remainder = 7%4;
```

### Exponent (**)

The exponent operator will multiply the number on the left by itself for the amount of times of the number on its right. That is, 4 ** 2 = 4 \* 4 and 2 ** 3 = 2 \* 2 \* 2. The area of a square that has sides with a length of `5` is equal to one side multiplied by another. For a square, all sides are equal, so:

```block
let side = 5;
let area = side * side;
```

But using the exponent operator, this is the same as:

```block
let side = 5;
let area = side ** 2;
```

The volume of a cube is three sides multiplied together. The two volumes are the same:

```block
let side = 5;
let volume1 = side * side * side;
let volume2 = side ** 3;
```

## 절댓값

When you want to know how much a number is without it's *sign* (+/-). The absolute value of -5 is 5 and the the absolute value 5 is also 5. The absolute value is sometimes called the *magnitude*.

```block
let item = Math.abs(-5);
```

## 두 수 중 작은/큰 값

You can get the smaller or the bigger of two numbers with the min() and max() functions.

* 2 와 9 중에서 작은 값: **Math.min(2, 9)** 로 표현할 수 있고, 그 결과 값은 2와 같습니다.
* 3 과 9 중에서 큰 값: **Math.max(3, 9)** 로 표현할 수 있고, 그 결과 값은 9와 같습니다.

```block
let minval = Math.min(0, 1);
let maxval = Math.max(8, 2);
```

## 랜덤 값

Make up any number from a minimum value to a some maximum value. If you want a random number up to 100, say: **Math.random(100)**.

```block
let myRandom = Math.random(5);
```

## 추가 참고

[랜덤](/reference/math/random)