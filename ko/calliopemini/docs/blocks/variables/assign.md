# 대입 연산자

Use an equals sign to make a [variable](/blocks/variables/var) store the [number](/reference/types/number) or [string](/reference/types/string) you say.

어떤 값을 저장시키기 위해 등호 기호를 사용하면, 그 기호를 *대입 연산자*라고 부르고, 그 변수에 저장 시킨 것을 <0>값<0>이라고 부릅니다.</p> 

### 변수에 수(정수) 저장하기

이 프로그램은 `item` 변수에 `5` 를 저장한 다음, item 변수에 저장되어있는 값을 [LED 스크린](/device/screen) 에 출력합니다.

```blocks
let item = 5
basic.showNumber(item)
```

### 변수에 문자열 저장하기

이 프로그램은 `name` 변수에 `Joe` 를 저장한 다음, name 변수에 저장되어있는 값을 [LED 스크린](/device/screen) 에 출력합니다.

```blocks
let name = "Joe"
basic.showString(name);
```

### Notes

You can use the assignment operator with variables of every [type](/reference/types). A *type* is which kind of thing a variable can store, like a number or string.

### 참고 항목

[variable](/blocks/variables/var), [types](/reference/types)