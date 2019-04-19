# 계속 실행 검사

계속 실행 조건이 거짓(false)이면 프로그램 실행을 중단합니다.

```sig
control.assert(false)
```

계속 실행 조건 블록에서 어떤 조건을 검사하고, 그 결과가 거짓(false)인 경우 프로그램 실행을 중단시킬 수 있습니다. 실행이 중단된 오류 번호는 실패 메시지와 함께 시리얼포트로 출력됩니다.

## 매개 변수

* **cond**. [불(참/거짓)](/types/boolean) 값. 참(true) 이면 계속 실행, 거짓(false)이면 프로그램 실행을 중단시킵니다!
* **msg**. 옵션 [문자열](/types/string). 중단 이유를 설명하는 메시지 내용

## 예시

다음은 `P0` 핀에 연결된 센서에 low (`0`) 신호가 입력되면 프로그램 실행을 중지하는 예시입니다.

```blocks
basic.forever(() => {
    control.assert(pins.digitalReadPin(DigitalPin.P0) == 1)
    basic.pause(1000)
})
```

## 참고 항목

[panic](/reference/control/panic)