# 페이드 아웃

LED 가 꺼질 때까지, [LED 스크린](/device/screen) 의 밝기를 점점 어둡게 만듭니다.

```sig
led.fadeOut(700);
```

### 매개 변수

* ms - [Number](/reference/types/number); the speed that the screen brightness is decreased, expressed in milliseconds (1,000 milliseconds = 1 second). 작은 값 일수록 스크린은 더 빨리 어두워집니다.

### 예시: 은은하게 꺼지는 A

다음은 스크린 밝기를 최대로 만든 후, 문자 A 를 출력하고 밝기를 점점 줄여갑니다.:

```blocks
led.setBrightness(255)
basic.showString("A", 1000)
led.fadeOut(1000)
```

### 참고 항목

[LED 스크린 밝기](/reference/led/brightness), [페이드 인](/reference/led/fade-in), [LED 스크린 밝기 설정](/reference/led/set-brightness)