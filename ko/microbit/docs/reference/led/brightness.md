# LED 스크린 밝기

[LED 스크린](/device/screen) 의 밝기 설정값을 읽어옵니다. 먼저 *LED 스크린이 켜진 후* 에 동작합니다.

```sig
led.brightness();
```

## 리턴값

* [수(정수)](/types/number). LED 스크린이 켜진 후, 스크린 밝기 설정값. `0` (가장 어두움) 부터 `255` (가장 밝음) 까지의 정수 값 예를 들어, 값 `127` 은 LED 스크린이 켜졌을 때, 최대 밝기의 반 정도 밝기로 켜진다는 것을 의미합니다.

## 예시: 가장 밝은 밝기

다음은 LED 스크린이 켜 진 후(이미 켜져 있는 경우), 스크린 밝기 설정값을 최대로 만드는 예시입니다.

```blocks
if (led.brightness() < 255) {
    led.setBrightness(255)
}
```

## 예시: LED 스크린 밝기 바꾸기

다음 프로그램은 스크린의 밝기를 100%(255) 로 설장합니다. 그 다음에 가운데 위치(`2, 2`) 에 있는 LED 를 켜고, 1 초 후 스크린 밝기를 50% (128) 로 바꿉니다.

```blocks
led.setBrightness(255)
led.plot(2, 2)
basic.pause(1000)
led.setBrightness(led.brightness() / 2)
```

## 참고 항목

[LED 스크린 밝기 설정](/reference/led/set-brightness), [페이드 인](/reference/led/fade-in), [페이드 아웃](/reference/led/fade-out)