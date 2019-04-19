# @extends

## #examples

## 예시: 변수에 저장되어있는 값 출력하기

대입 연산자를 사용하면 [변수](/blocks/variables/var)에 원하는 값을 저장할 수 있습니다. 값 설정 블록을 사용해서, 변수에 저장되어있는 값을 0 에서 1로 바꿔보세요. 그 다음에, 변수에 새로 저장된 값을 LED 스크린으로 출력해보세요. 다음과 같이 말이죠:

```blocks
let x = 0;
x += 1;
basic.showNumber(x);
```