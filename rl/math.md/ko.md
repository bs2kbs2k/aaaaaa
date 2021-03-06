# 계산

Using [numbers](/types/number), number operators, and math functions.

## Numeric values: 0, 1, 2, 6.7, 10.083...

Just numbers by themselves. Sometimes these are called *numeric literals*.

### Integers: whole numbers

```block
let num = 0;
num = 0;
num = 1;
num = 2;
```

### Floating point: numbers with a fractional part #floatingpoints

Numbers can have their fractional part too. The decimal point is between the digits of the number. But, *floating point* numbers have the decimal point at any spot between digits, like: 3.14159 or 651.75.

```block
let num = 0
num = 6.7
num = 10.083
```

### 산술 연산 (+, -, *, /)

The operations for basic arithmetic: add, subtract, multiply, and divide.

```block
let more = 0+1;
let less = 0-1;
let twice = 1*2;
let divide = 8/4;
```

### Remainder (%)

This is a extra operator for division. You can find out how much is left over if one number doesn't divide into the other number evenly.

We know that 4 / 2 = 2, so 2 divides into 4 evenly. But, 5 / 2 = 2 with a remainder of 1. So, the remainder operation, 5 % 2 = 1, gives the number that's left over from a division operation.

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

## Square root

The square root of a number is another number that when multiplied by itself it becomes the original number. You know that `2 * 2` equals `4` so the square root of `4` is `2`. It's called a *square root* because the area of a *square* is the length of two equal sides multplied together. The *root* is the length of a side.

```block
let side = 5
let square = side * side
let root = Math.sqrt(side)
```

## 절댓값

When you want to know how much a number is without its *sign* (+/-). The absolute value of -5 is 5 and the absolute value of 5 is also 5. The absolute value is sometimes called the *magnitude*.

```block
let item = Math.abs(-5);
```

## Minimum and maximum of two values

You can get the smaller or the bigger of two numbers with the [min](/reference/math/min) and [max](/reference/math/max) functions.

* The minimum of 2 and 9: **Math.min(2, 9)** equals 2.
* The maximum of 3 and 9: **Math.max(3, 9)** equals 9.

```block
let minval = Math.min(0, 1);
let maxval = Math.max(8, 2);
```

## 랜덤 값

원하는 최댓값 범위 이내에서 임의의 랜덤 값을 뽑아줍니다. 100 이하의 범위에서 임의의 정수 값을 얻고 싶은 경우에는: **Math.randomRange(0, 100)** 라고 작성하면 됩니다.

```block
let myRandom = Math.randomRange(0, 5);
```

## 참고 항목 #seealso

[abs](/reference/math/abs), [min](/reference/math/min), [max](/reference/math/max), [randomRange](/reference/math/random-range)