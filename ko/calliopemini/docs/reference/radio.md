# 라디오

라디오 패킷을 이용해 데이터를 송수신합니다.

```cards
radio.sendNumber(0);
radio.sendValue("name", 0);
radio.sendString("");
radio.onDataPacketReceived(() => {

});
radio.setGroup(0);
radio.setTransmitPower(7);
radio.setTransmitSerialNumber(false);
radio.writeReceivedPacketToSerial();
```

```package
라디오
```

### 참고 항목

[라디오 정수 전송](/reference/radio/send-number), [라디오 값 전송](/reference/radio/send-value), [라디오 문자열 전송](/reference/radio/send-string), [라디오 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 그룹 설정](/reference/radio/set-group), [라디오 전송 강도 설정](/reference/radio/set-transmit-power), [라디오 시리얼 번호 전송 설정](/reference/radio/set-transmit-serial-number), [라디오 수신 패킷을 시리얼로 전송](/reference/radio/write-received-packet-to-serial)