# 큰 이미지 만들기

[큰 이미지](/reference/images/image) (사진) 를 만들어보세요. 이미지는 @boardname@ 의 [LED 스크린](/device/screen) 으로 출력됩니다. 큰 이미지는 이미지 사각형 두 개를 붙여 만든 크기입니다. 각 사각형은 한 면의 길이가 LED 5개 크기이며, 정사각형 형태로 배치되어 있습니다.

```sig
images.createBigImage(`
    . . # . .   . . # . .
    . # # # .   . . # . .
    # . # . #   # . # . #
    . . # . .   . # # # .
    . . # . .   . . # . .
    `);
```

## 매개 변수

* `LED 상태`. LED 스크린에서 켜고 끌 배치를 표현한 [문자열](/types/string).

## 예시: 화살표 뒤집기

다음은 북쪽 화살표와 남쪽 화살표를 이어 붙인 것과 같은 큰 이미지를 만드는 예시 코드입니다. `A` 버튼을 누르면, LED 스크린에 큰 이미지의 `0` 번째 위치부터 북쪽 화살표 부분이 출력됩니다. `B` 버튼을 누르면, LED 스크린에 큰 이미지의 `5` 번째 위치부터 남쪽 화살표 부분이 출력됩니다.

```blocks
let arrows = images.createBigImage(`
    . . # . .   . . # . .
    . # # # .   . . # . .
    # . # . #   # . # . #
    . . # . .   . # # # .
    . . # . .   . . # . .
    `);
input.onButtonPressed(Button.A, () => {
    arrows.showImage(0);
});
input.onButtonPressed(Button.B, () => {
    arrows.showImage(5);
});
```

## 참고 항목

[이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image), [애니메이션 출력](/reference/basic/show-animation)