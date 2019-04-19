# 라디오 정수 수신

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 을 사용하세요.

같은 `라디오(radio)` 그룹에 있는 @boardname@ 에서 전송된 수를 읽어옵니다.

```sig
radio.receiveNumber();
```

## 리턴값

* [수(정수)](/types/number). @boardname@ 가 수신한 수(정수). 수신된 데이터에 수(정수)가 포함되어있지 않은 경우 `0` 을 리턴합니다.

## 예시: 간단한 수 수신기

다음은 다른 @boardname@ 가 전송한 수(정수) 값을, LED 그래프로 그려주는 예시 코드입니다.

```blocks
radio.onDataReceived(() => {
    led.plotBarGraph(radio.receiveNumber(), 1023);
})
```

## 예시: 빛 센서 값 수신기

다음은 [빛 센서](/reference/radio/send-number) 에서 전달된 빛 센서값을, 숫자로 출력하는 예시 코드입니다.

```blocks
radio.setGroup(99)
basic.forever(() => {
    let level = radio.receiveNumber()
    basic.showNumber(level)
})
```

## 예시: 메일 로봇

다음은 [빛 센서](/reference/radio/send-number) 에서 전달된 빛 센서값이 어떤 값 보다 클 때, **ALERT** 문자열을 출력하는 예시 코드입니다. 메일이 도착한 시간을 알고 싶은 경우, 빛 센서 값을 전송하도록 할 수 있습니다. 메일을 열면 알 수 있게 됩니다. 친구에게 보내는 선물 상자와 같은, 일반 상자에도 적용시킬 수 있습니다.

```blocks
radio.setGroup(99)
let max = 0
basic.forever(() => {
    let level = radio.receiveNumber()
    if (level > max) {
        max = level
    }
    if (max > 10) {
        basic.showString("ALERT")
    }
})
```

## 참고 항목

[라디오 정수 전송](/reference/radio/send-number), [라디오 데이터 수신하면 실행](/reference/radio/on-data-received)

```package
radio
```