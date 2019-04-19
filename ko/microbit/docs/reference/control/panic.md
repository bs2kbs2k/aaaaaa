# 오류 발생

오류 번호를 출력하고 프로그램 실행을 중단합니다.

```sig
control.panic(0)
```

보드에 오류 정보를 출력할 수 있는 방법이 있는 경우, `||control:panic||` 가 동작해 오류 번호를 출력하도록 할 수 있습니다.

`||control:panic||` 를 사용하면 프로그램 실행이 중단됩니다. 뭔가 잘못되었거나 정상적으로 더 이상 실행할 수 없을 때, 이 기능을 사용하면 됩니다.

## 매개 변수

* **code**. 오류 번호를 나타내는 [수(정수)](/types/number). 프로그램에서 발생한 오류 상황을 알아낼 수 있습니다.

### ~hint

**시스템 에러 코드**

@boardname@ 시스템 소프트웨어에 의해서 사용될 수 있는 오류 코드들이 내장되어있습니다. ```panic()``` 이 함수는 고급 사용자용입니다. @boardname@ 시스템에서 사용되지 않는, 다른 번호의 코드를 주의해서 사용해야합니다.

### ~

## 예시

다음 코드는 `P0` 핀으로부터 입력된 값이 `10` 보다 작은 경우, 임의로 선택한 'code red' 번호를 출력하는 예시입니다.

```blocks
let codeRed = 1110;
let codeBlue = 1111;

if (pins.analogReadPin(AnalogPin.P0) < 10) {
    control.panic(codeRed)
}
```

## 참고 항목

[계속 실행 검사](/reference/control/assert), [오류 코드](/device/error-codes)