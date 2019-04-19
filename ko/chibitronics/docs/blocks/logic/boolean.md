# 불(참/거짓) 논리

불 값(참/거짓)은 2가지 값 중 하나의 값만 가질 수 있습니다: `참(true)`; `거짓(false)`. 불 (논리) 연산자 (*and*, *or*, *not*) 는 불 값을 입력 받아 계산하고, 그 결과로 새로운 불 값을 만들어낸다. Comparison operators on other types ([numbers](/types/number), [strings](/types/string) yields a Boolean value.

다음 블록들은 불 값 참(true), 거짓(false)을 의미하며, 불 값이 들어갈 수 있는 어느 곳에나 붙여 넣을 수 있습니다.

```block
let on = true;
```

The next three blocks represent the three Boolean (logic) operators:

```todoblock
let and = true && false;
let or = true || false;
let not = !true;
```

The next six blocks represent comparison operators that yield a Boolean value. Most comparisons you will do involve [numbers](/types/number):

```block
let equality = 42 == 42;
let inequality = 42 != 42;
let lowerThan = 42 < 0;
let greaterThan = 42 > 0;
let lowerOrEqualThan =42 <= 0;
let greaterOrEqualThan = 42 >= 0;
```

Boolean values and operators are often used with an [if](/blocks/logic/if) or [while](/blocks/loops/while) statement to determine which code will execute next. For example:

## Functions that return a Boolean

Some functions return a Boolean value, which you can store in a Boolean variable. For example, the following code gets the on/off state of `point (1, 2)` and stores this in the Boolean variable named `on`. Then the code clears the screen if `on` is `true`:

## 불(참/거짓) 논리 연산자

Boolean operators take Boolean inputs and evaluate to a Boolean output:

### Conjunction: `A and B`

`A and B` evaluates to `true` if-and-only-if both A and B are true:

```block
let off = false && false;
let off2 = false && true;
let off3 = true && false;
let on = true && true;
```

### Disjunction: `A or B`

`A or B` evaluates to `true` if-and-only-if either A is true or B is true:

```block
let off = false || false;
let on = false || true;
let on2 =true || false;
let on3 = true || true;
```

### Negation: `not A`

`not A` evaluates to the opposite (negation) of A:

```todoblock
let on = !false;
let off = !true;
```

## #examples