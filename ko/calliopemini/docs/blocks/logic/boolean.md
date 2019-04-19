# 불(참/거짓) 논리

참(true) 또는 거짓(false)

불 값(참/거짓)은 2가지 값 중 하나의 값만 가질 수 있습니다: `참(true)`; `거짓(false)`. 불 (논리) 연산자 (*and*, *or*, *not*) 는 불 값을 입력 받아 계산하고, 그 결과로 새로운 불 값을 만들어낸다. Comparison operators on other types ([numbers](/reference/types/number), [strings](/reference/types/string) yields a Boolean value.

다음 블록들은 불 값 참(true), 거짓(false)을 의미하며, 불 값이 들어갈 수 있는 어느 곳에나 붙여 넣을 수 있습니다.

```blocks
true;
false;
```

The next three blocks represent the three Boolean (logic) operators:

```blocks
true && false;
true || false;
!true;
```

The next six blocks represent comparison operators that yield a Boolean value. Most comparisons you will do involve [numbers](/reference/types/number):

```blocks
42 == 0;
42 != 0;
42 < 0;
42 > 0;
42 <= 0;
42 >= 0;
```

Boolean values and operators are often used with an [if](/blocks/logic/if) or [while](/blocks/loops/while) statement to determine which code will execute next. For example:

### Functions that return a Boolean

Some functions return a Boolean value, which you can store in a Boolean variable. For example, the following code gets the on/off state of `point (1, 2)` and stores this in the Boolean variable named `on`. Then the code clears the screen if `on` is `true`:

### 불(참/거짓) 논리 연산자

Boolean operators take Boolean inputs and evaluate to a Boolean output:

### Conjunction: `A and B`

`A and B` evaluates to `true` if-and-only-if both A and B are true:

```blocks
false && false == false;
false && true == false;
true && false == false;
true && true == true;
```

### Disjunction: `A or B`

`A or B` evaluates to `true` if-and-only-if either A is true or B is true:

```blocks
false || false == false;
false || true == true;
true || false == true;
true || true == true;
```

### Negation: `not A`

`not A` evaluates to the opposite (negation) of A:

```blocks
!false == true;
!true == false;
```

### 예시

다음은 `1 , 1` 와 `2 , 2` 위치의 LED가 둘 다 모두 켜져있을 때, `3 , 3` 위치의 LED를 켜는 예시입니다.:

```blocks
if (led.point(1,1) && led.point(2,2)) {
   led.plot(3,3)
}
```

### Comparisons of numbers and strings

어떤 두 수를 서로 비교하면, 그 계산 결과로 참(true) 또는 거짓(false)의 불 값을 얻게 됩니다. 다음 코드에서 `x < 5` 비교식을 살펴보세요.:

```blocks
let x = Math.random(5)
if(x < 5) {
   basic.showString("low");
} else { 
   basic.showString("high");
} 
```

See the documentation on [Numbers](/reference/types/number) for more information on comparing two Numbers. You can also [compare strings](/reference/types/string-functions) using the `equals` function.

### 참고 항목

[if](/blocks/logic/if), [while](/blocks/loops/while), [number](/reference/types/number)