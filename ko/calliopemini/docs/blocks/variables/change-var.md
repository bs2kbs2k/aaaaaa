# 값 변경

지역 변수와 전역 변수에 값을 저장합니다.

### @parent blocks/change-value

변수에 저장되어 있는 값 변경

```blocks
let x = 0
x += 1
```

### 변수 선언

어떤 변수<0>에 원하는 값을 저장시키기 위해, 대입 연산자를 사용하세요. 변수에 저장되어있는 값을 기본 값 0에서 1로 변경해보세요. 다음과 같이 하면 됩니다.</p> 

```blocks
let x = 0
x += 1
```

### 예시

대입 연산자를 사용하면 [변수](/blocks/variables/var)에 원하는 값을 저장할 수 있습니다. 값 설정 블록을 사용해서, 변수에 저장되어있는 값을 0 에서 1로 바꿔보세요. 그 다음에, 변수에 새로 저장된 값을 LED 스크린으로 출력해보세요. Like this:

```blocks
let x = 0;
x += 1;
basic.showNumber(x);
```

### Notes

* You can use the assignment operator with variables of each of the supported [types](/reference/types).

### 참고 항목

[variable](/blocks/variables/var), [types](/reference/types)