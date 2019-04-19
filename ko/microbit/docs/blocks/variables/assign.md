# 대입 연산자

어떤 [변수](/blocks/variables/var) 에 [수(정수)](/types/number) 나 [문자열](/types/string) 을 저장시키려면, 등호(=) 기호를 사용하면 됩니다.

어떤 값을 저장시키기 위해 등호 기호를 사용하면, 그 기호를 *대입 연산자*라고 부르고, 그 변수에 저장 시킨 것을 <0>값<0>이라고 부릅니다.</p> 

## 변수에 수(정수) 저장하기

이 프로그램은 `item` 변수에 `5` 를 저장한 다음, item 변수에 저장되어있는 값을 [LED 스크린](/device/screen) 에 출력합니다.

```blocks
let item = 5
basic.showNumber(item)
```

## 변수에 문자열 저장하기

이 프로그램은 `name` 변수에 `Joe` 를 저장한 다음, name 변수에 저장되어있는 값을 [LED 스크린](/device/screen) 에 출력합니다.

```blocks
let name = "Joe"
basic.showString(name);
```

## 참고

대입 연산자는, 원하는 모든 [데이터형](/types)의 변수들에 대해서 사용할 수 있습니다. *데이터형*은 수나 문자열과 같은 저장하는 데이터의 종류를 의미합니다.

## 참고 항목

[변수](/blocks/variables/var), [데이터형](/types)