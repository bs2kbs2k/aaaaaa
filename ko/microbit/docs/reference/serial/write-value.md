# write Value

Write a **name:value** pair and a newline character (`\r\n`) to the [serial](/device/serial) port.

```sig
serial.writeValue("x", 0);
```

It is common when reporting or recording data to use a *Name Value Pair* (NVP). They appear as a text output string in the form of a *name* and a *value* together. The name and the value are separated in the string with a *colon*, `:`. A name value pair reporting a temperature of `-15` degrees could look like:

`temperature:-15`

Associating a name with a value helps to identify related data when different data sources are recorded. For example, if you're reporting both temperature and light intensity, the *name:value* format helps spreadsheets or other data analysis programs distingush between them and group the same types of values together properly. Reporting two data sources might look like this in the output:

    temperature:-15
    temperature:-12
    light:154
    temperature:-11
    light:152
    

## 매개 변수

* `변수 이름`. 시리얼통신 포트로 전송시킬 [문자열](/types/string)
* `값`. 시리얼통신 포트로 전달시킬 [정수](/types/number)

## 예시: 실시간 스트리밍 데이터 전송하기

아래의 코드는, 10 초 마다 온도 센서값과 빛 센서값을 시리얼포트를 통해 전달합니다.

```blocks
basic.forever(() => {
    serial.writeValue("temp", input.temperature())
    serial.writeValue("light", input.lightLevel())
    basic.pause(10000);
})
```

### ~hint

[값 전송](/reference/radio/send-value) 함수는 변수 이름을 의미하는 문자열과 수(값)를 쌍으로 묶어 전송합니다. 시리얼통신 포트를 통해 전송된 데이터들은 다른 @boardname@ 를 통해 수신이 가능하며, 수신한 데이터들을 `시리얼통신 값 전송` 을 이용해 시리얼통신 포트로 직접 전송할 수 있게 됩니다.

### ~

## 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 정수 전송](/reference/serial/write-number), [시리얼통신 값 전송](/reference/radio/send-value)