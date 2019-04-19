# 라디오 수신 패킷을 시리얼로 전송

`라디오(radio)` 를 통해 수신한 마지막 데이터 패킷을 JSON 포맷으로 시리얼 출력합니다. [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 블록 안에서 콜백(callback) 실행되어야 합니다.

```sig
radio.writeReceivedPacketToSerial();
```

## 시리얼 통신 데이터 출력 형식

The format for received data when these send functions are used:

- [send number](/reference/radio/send-number): ```{v:ValueSent,t:MicrobitTimeAlive,s:SerialNumber}```
- [send value](/reference/radio/send-value): ```{v:ValueSent,t:MicrobitTimeAlive,s:SerialNumber,n:"Name"}```
- [send string](/reference/radio/send-string): ```{t:MicrobitTimeAlive,s:SerialNumber,n:"Text"}```

### ~hint

The serial number value sent in the packet is set to `0` unless transmission of the serial number is enabled with `||radio:radio set transmit serial number||`.

### ~

## 예시

다음은 ```라디오``` 기능을 통해 데이터가 수신되었을 때( `A` button on the second @boardname@), this program sends temperature data to the serial port.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(input.temperature());
    radio.sendValue("temperature", input.temperature());
    radio.sendString("It's warm now");


});
radio.onDataPacketReceived(() => {
    radio.writeReceivedPacketToSerial();
});
```

다음은 `A` 버튼이 눌렸을 때, 시리얼 통신으로 데이터를 보내는 예시입니다.:

```json
{"t":323,"s":0,"v":27}
{"t":325,"s":0,"n":"temperature","v":27}
{"t":326,"s":0,"n":"It's warm now"}
```

## 참고 항목

[send number](/reference/radio/send-number), [send value](/reference/radio/send-value), [send string](/reference/radio/send-string), [on data packet received](/reference/radio/on-data-packet-received), [set transmit serial number](/reference/radio/set-transmit-serial-number)

```package
radio
```