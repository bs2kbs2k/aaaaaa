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

## 매개 변수

* `LED 상태`. LED 스크린에서 켜고 끌 배치를 표현한 [문자열](/types/string).

## 예시: 화살표 뒤집기

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

## 참고 항목

[이미지](/reference/images/image), [큰 이미지 만들기](/reference/images/create-big-image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image), [애니메이션 출력](/reference/basic/show-animation)