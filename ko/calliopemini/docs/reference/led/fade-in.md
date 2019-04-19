# 페이드 인

가장 밝게 될 때까지, [LED 스크린](/device/screen) 의 밝기를 점점 밝게 만듭니다.

```sig
led.fadeIn(700);
```

### 매개 변수

* ms - [Number](/reference/types/number); the speed by which the screen brightness is increased, expressed in milliseconds (1,000 milliseconds = 1 second). 작은 값 일수록 스크린은 더 빨리 밝아집니다.

### 예시: 은은하게 깜박이는 점

다음은 스크린의 가운데에 있는 LED 를 켜고, 밝기를 점점 밝게 했다가 다시 어둡게 만드는 코드입니다. (가운데 LED 는 5 번 점등됩니다.)

```blocks
led.plot(2, 2)
for (let i = 0; i < 5; i++) {
    led.setBrightness(0)
    led.fadeIn(100)
    basic.pause(100)
    led.fadeOut(100)
}
```

### 참고 항목

[LED 스크린 밝기](/reference/led/brightness), [페이드 아웃](/reference/led/fade-out), [LED 스크린 밝기 설정](/reference/led/set-brightness)