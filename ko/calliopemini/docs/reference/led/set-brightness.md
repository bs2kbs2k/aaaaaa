# LED 스크린 밝기 설정

[LED 스크린](/device/screen) 이 켜졌을 때의 밝기를 설정합니다.

```sig
led.setBrightness(121)
```

### 매개 변수

* `value` is a [number](/reference/types/number) that means how bright the screen is when it is turned on, from `0` (darkest) to `255` (brightest). 예를 들어, 값 `127` 은 LED 스크린이 켜졌을 때, 최대 밝기의 반 정도 밝기로 켜진다는 것을 의미합니다.

### 예시: LED 스크린 밝기 바꾸기

다음은 LED 스크린의 밝기를 100% (`255`) 로 설정하는 예시입니다. 스크린의 가운데에 있는 LED (`2, 2`) 를 켠 후, 1초를 기다립니다. 그 다음에 LED 스크린 밝기를 50% (`128`) 로 변경합니다.:

```blocks
led.setBrightness(255)
led.plot(2, 2)
basic.pause(1000)
led.setBrightness(led.brightness() / 2)
```

### 참고 항목

[LED 스크린 밝기](/reference/led/brightness), [페이드 인](/reference/led/fade-in), [페이드 아웃](/reference/led/fade-out), [LED 스크린](/device/screen)