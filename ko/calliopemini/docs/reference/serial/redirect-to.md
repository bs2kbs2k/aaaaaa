# 시리얼통신 동적 인스턴스 설정

`USBTX` 와 `USBRX` 이외의 다른 핀을 사용할 수 있도록, 시리얼통신 인스턴스를 동적으로 변경합니다.

```sig
serial.redirect(SerialPin.P0, SerialPin.P0, BaudRate.BaudRate115200);
```

### 매개 변수

* `tx`: 시리얼통신 데이터를 전송시킬 [시리얼통신 핀](/device/pins) 
* `rx`: 시리얼통신 데이터를 수신시킬 [시리얼통신 핀](/device/pins) 
* `baud rate`: 시리얼통신 데이터 송수신 속도(`9600` 또는 `115200`)

### 예시

다음 코드는 `A` 버튼을 눌렀을 때 시리얼통신 송수신 인스턴스를 변경시키는 예시입니다. A 버튼을 눌러 코드가 실행되면, `P1` 포트는 시리얼통신 송신 포트로 설정되고 `P2` 포트는 수신 포트로 설정되며 시리얼통신 속도는 `9600` 로 변경됩니다.

```blocks
input.onButtonPressed(Button.A, () => {
    serial.redirect(SerialPin.P1, SerialPin.P2, BaudRate.BaudRate9600);
});
```

### 참고 항목

[시리얼통신](/device/serial)