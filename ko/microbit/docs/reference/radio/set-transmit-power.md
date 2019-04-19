# 라디오 출력 강도 설정

Make the `radio` signal of the @boardname@ stronger or weaker. It can be as weak as `0` and as strong as `7`. Default is `6`.

`라디오(radio)` 신호 출력 강도의 단위는, **dBm** 또는 **데시벨-밀리와트(decibel-milliwatts)** 입니다. 신호 출력 강도 `0` 은 -30 dBm 정도로 측정되고, `7` 은 +4 dBm 정도로 측정됩니다.

```sig
radio.setTransmitPower(7);
```

## 도달 범위

@boardname@ 에서 신호 출력 강도 `7` 로 신호를 전송하고, 주변에 장애물과 컴퓨터들이 없는 경우, @boardname@ 신호가 대략 70 미터(약 230 피트) 정도까지 전송될 수 있습니다.

## 매개 변수

* `power`. [수(정수)](/types/number). 라디오 신호 출력 강도를 나타내는 `0` 부터 `7` 사이의 값.

## 시뮬레이터

이 함수는 @boardname@ 에서만 정상적으로 동작하고, 웹브라우저에서는 동작하지 않습니다.

## 예시

다음은 `라디오(radio)` 신호 출력 강도를 최대로 하는 예시입니다.

```blocks
radio.setTransmitPower(7)
```

## 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 정수 전송](/reference/radio/send-number), [라디오 값 전송](/reference/radio/send-value), [라디오 문자열 전송](/reference/radio/send-string)

```package
radio
```