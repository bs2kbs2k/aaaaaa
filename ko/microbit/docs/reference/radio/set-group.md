# 라디오 그룹 설정

`라디오(radio)` 송수신에 사용할, 라디오 그룹을 설정합니다. 그룹은 마치 TV 채널과 비슷합니다. (@boardname@ 는 한 번에 한 그룹에서만 데이터를 송수신 할 수 있습니다.) 그룹은 TV 채널 번호와 비슷합니다.

라디오 그룹 번호를 지정하지 않으면, 자체적으로 그룹 번호를 설정할 것입니다. 서로 다른 여러 개의 @boardname@ 들에 같은 프로그램을 업로드하면, 같은 그룹으로 묶여 서로 서로 통신할 수 있게 됩니다.

```sig
radio.setGroup(0);
```

## 매개 변수

* `id`. [수(정수)](/types/number). `0` 부터 `255` 범위의 값.

## 시뮬레이터

이 함수는 @boardname@ 에서만 정상적으로 동작하고, 웹브라우저에서는 동작하지 않습니다.

## 예시

다음은 라디오 그룹을 128 로 설정합니다.

```blocks
radio.setGroup(128)
```

## 참고 항목

[시리얼통신 구분 문자 받으면 실행](/reference/radio/on-data-packet-received), [시리얼통신 정수 전송](/reference/radio/send-number), [시리얼통신 값 전송](/reference/radio/send-value), [시리얼통신 문자열 전송](/reference/radio/send-string)

```package
radio
```