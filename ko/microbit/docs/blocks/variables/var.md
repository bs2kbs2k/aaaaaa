# 지역 변수

지역 변수 선언(정의)하고 사용하기

## @parent language

변수는 데이터를 저장하고 가져올 수 있는 공간의 이름입니다. 변수는 이름, [데이터형](/types), 값을 가집니다.:

* *이름*은 변수를 사용할 때 사용하는 이름입니다.
* *데이터형*은 변수에 저장할 수 있는 데이터의 종류를 의미합니다.
* *값*은 변수에 저장되어있는 것을 의미합니다.

## 변수 명령문

블록 편집기 내에서 변수 명령문을 이용해 변수를 만들고, [대입 연산자](/blocks/variables/assign) 를 이용해 원하는 값을 저장시킬 수 있습니다.

예를 들어, 다음 코드는 `x` 변수에 정수 `2` 를 저장합니다.:

```blocks
let x = 2;
```

블록 편집기에서 새 변수를 정의해서 만드는 방법은 다음과 같습니다.:

1. `변수`를 누릅니다.

2. 필요에 따라, 변수 이름을 바꿉니다.

3. [대입 연산자](/blocks/variables/assign)의 오른쪽에서, 원하는 데이터형을 드래그 한 후, 아래 쪽 화살표를 눌러 변수의 이름을 변경할 수 있습니다.

LED [빛 센서 값](/reference/led/brightness) 함수를 통해 리턴된 값을 저장하며, 변수를 만드는 방법은 다음과 같습니다.

```blocks
let b = led.brightness();
```

## 변수 사용하기

사용하기 전에 먼저 변수를 정의해서 선언하면, 변수에 값을 저장하거나, 변수에 저장되어있는 값을 읽어와 사용할 수 있습니다. 예를 들어, 다음 코드는 `counter` 변수에 저장되어있는 값을 LED 스크린에 출력해줍니다.:

```blocks
let counter = 1;
basic.showNumber(counter);
```

변수에 저장되어 있는 값을 바꾸기 위해서 대입 연산자를 사용합니다. 다음 코드는 `counter` 변수에 1을 저장한 다음, `counter` 변수에 저장된 값을 10 만큼 증가시키는 코드입니다.:

```blocks
let counter = 1;
counter = counter + 10;
basic.showNumber(counter);
```

## 변수를 왜 사용하나요?

데이터를 저장해두었다가, 다시 사용하려면, 변수가 필요하게 됩니다. 카운터는 아주 좋은 예입니다.

```blocks
let counter = 0;
input.onButtonPressed(Button.A, () => { 
  counter = counter + 1;
  basic.showNumber(counter);
});
```

## 지역 변수

지역 변수는, 그 변수가 정의되어 있는 함수나 코드 블록 안에서만 인식됩니다. 예를 들어:

```blocks
// x does NOT exist here.
if (led.brightness() > 128) {
  // x exists here
  let x = 0;
}
```

### 참고

* 기본 변수 이름을 사용할 수 있지만, 저장되는 값의 의미를 파악하기 쉬운 이름을 사용하는 것이 가장 좋습니다. 편집기 내에서 변수 이름을 바꾸려면, 변수 옆에 있는 화살표를 누른 후 "새 변수"를 누르면 됩니다.

## 참고 항목

[데이터형](/types), [대입 연산자](/blocks/variables/assign)