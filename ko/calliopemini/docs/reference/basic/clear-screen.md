# LED 스크린 지우기

[LED 스크린](/device/screen) 의 모든 LED 불빛을 끕니다.

```sig
basic.clearScreen()
```

### 예시: 하트 모양 지우기

다음은 LED 스크린에 하트 모양을 출력한 후, LED 스크린의 모든 LED 불 빛을 끄는 예시입니다.

```blocks
basic.showLeds(`
. # . # . 
# # # # # 
# # # # # 
. # # # . 
. . # . . 
`)
basic.clearScreen()
```

### 참고 항목

[LED 밝기 설정](/reference/led/set-brightness), [LED 끄기](/reference/led/unplot), [LED 켜기](/reference/led/plot), [LED 이미지](/reference/images/image)