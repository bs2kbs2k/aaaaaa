# LED 출력

[이미지](/reference/images/image) 를 @boardname@ 의 [LED 스크린](/device/screen)을 통해 출력합니다. 참고: `기본 -> 이미지 출력`은 `기본 -> LED 출력`으로 대체되었습니다.

```sig
basic.showLeds(`
. . . . .
. # . # .
. . # . .
# . . . #
. # # # .
`)
```

## 매개 변수

* LED - 이미지를 표현할 수 있는 형태로 구성된 LED on/off 상태 (다음 참고)

## 예시: 스마일리

```blocks
basic.showLeds(`
. . . . .
. # . # .
. . # . .
# . . . #
. # # # .
`)
```

## 참고 항목

[애니메이션 출력](/reference/basic/show-animation), [이미지](/reference/images/image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image)