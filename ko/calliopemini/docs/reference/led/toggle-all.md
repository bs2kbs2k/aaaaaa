# LED 스크린 전체 반전

[LED 스크린](/device/screen) 의 모든 LED 상태를 반전시킵니다. - 켜져있던 LED 는 꺼지게 됩니다.; 꺼져있던 LED 는 켜지게 됩니다.

```sig
led.toggleAll()
```

### 매개 변수

* 없음

### 예시

다음은 (2, 2) 좌표에 있는 LED 만, 나머지와 반대로 켜지고 꺼지도록 만든 예시 코드입니다.

```blocks
basic.clearScreen()
led.plot(2, 2)
led.toggleAll()
```

```sim
basic.clearScreen()
led.plot(2, 2)
led.toggleAll()
```

### 참고 항목

[LED 반전](/reference/led/toggle), [LED 스크린](/device/screen), [LED 스크린 지우기](/reference/basic/clear-screen)