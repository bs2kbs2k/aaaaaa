# 불(참/거짓) 논리

A Boolean has one of two possible values: `true` or `false`. Boolean (logical) operators (*and*, *or*, *not*) take Boolean inputs and make another Boolean value. Comparison operators on other types ([numbers](/types/number), [strings](/types/string)) create Boolean values.

These blocks represent the `true` and `false` Boolean values, which can plug into anyplace a Boolean value is expected:

```block
true;
false;
```

다음 3가지 블록은 3개의 불(논리) 연산자를 나타냅니다.:

```block
true && false;
true || false;
!true;
```

The next six blocks represent comparison operators that yield a Boolean value. Most comparisons you will do involve [numbers](/types/number):

```block
42 == 0;
42 != 0;
42 < 0;
42 > 0;
42 <= 0;
42 >= 0;
```

불 값과 연산자들은 [만약](/blocks/logic/if) 이나 [참인 동안](/blocks/loops/while) 명령과 함께 사용되며, 조건에 따라 다음 코드를 실행할 지의 여부를 결정하기 위해 사용됩니다. 예를 들어:

### 불 값을 리턴하는 함수

함수에 따라서, 불 변수에 불 값을 저장해 리턴시킬 수 있습니다. 예를 들어, 다음 코드는 `위치 (1, 2)`의 on/off 상태를 읽어오고, 불 변수인 `on`에 저장합니다. 그 다음에 `on` 변수에 저장되어있는 불 값이 `true`인 경우, 화면을 지웁니다.:

### 불(논리) 연산자

불 (논리) 연산자는 불 값을 입력으로 받아, 불 값의 출력으로 계산(평가) 합니다.:

### 논리 교집합(and): `A and B`

`A and B` 는 `true` 로 평가(계산) 됩니다. A 와 B 의 평가 값이 모두 참(true) 인 경우만 참(true) 으로 계산(평가) 됩니다.:

```block
false && false == false;
false && true == false;
true && false == false;
true && true == true;
```

### 논리 합집합(or): `A or B`

`A or B` 는 `true` 로 평가(계산) 됩니다. A 와 B 의 평가 값 중 하나라도 참(true) 인 경우에 참(true) 으로 계산(평가) 됩니다.:

```block
false || false == false;
false || true == true;
true || false == true;
true || true == true;
```

### 논리 부정(not): `not A`

`not A` A의 평가 값을 반대(negation) 로 바꾸어 계산(평가) 됩니다.:

```block
!false == true;
!true == false;
```

## #examples