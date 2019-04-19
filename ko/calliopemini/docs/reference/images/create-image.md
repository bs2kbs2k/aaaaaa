# 이미지 만들기

[이미지](/reference/images/image) (사진) 를 만들어보세요. 이미지는 @boardname@ 의 [LED 스크린](/device/screen) 으로 출력됩니다.

```sig
images.createImage(`
. . # . .
. # # # .
# # # # #
. # # # .
. . # . .
`)
```

### 매개 변수

* `leds` is a [string](/reference/types/string) that says which LEDs on the screen should be on and which should be off.

### 예시: 화살표 뒤집기

`A` 버튼을 누르면, LED 스크린에 화살표 이미지가 출력됩니다. `B` 버튼을 누르면, LED 스크린에 위 아래가 반대로 바뀐 화살표 이미지가 출력됩니다.

```blocks
input.onButtonPressed(Button.A, () => {
    images.createImage(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `).showImage(0);
});
input.onButtonPressed(Button.B, () => {
    images.createImage(`
        . . # . .
        . . # . .
        # . # . #
        . # # # .
        . . # . .
        `).showImage(0);
});
```

### 참고 항목

[Getting Started](/getting-started), [image](/reference/images/image), [create big image](/reference/images/create-big-image), [show image](/reference/images/show-image), [scroll image](/reference/images/scroll-image), [show animation](/reference/basic/show-animation)