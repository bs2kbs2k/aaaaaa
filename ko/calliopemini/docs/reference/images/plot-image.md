# 이미지 플로트

이미지 플로트 함수.

[이미지](/reference/images/image) 를 @boardname@ 의 [LED 스크린](/device/screen) 에 출력해보세요.

### 자바스크립트

```sig
export function plotImage(_this: micro_bit.Image, xOffset: number)
```

### 매개 변수

* x offset - [Number](/reference/types/number); the horizontal starting point of an image; use 0 for the first frame of the image, 5 for the second frame of the image, 10 for the third frame and so on.

### `이미지 출력` 과의 차이점

`이미지 출력` 함수는 400 밀리초가 지나야 다음 이미지를 출력하는 반면, `이미지 플로트` 는 그러한 시간 지연이 없습니다.

### 예시

```blocks
let img = images.createImage(`
# . . . # # . . . #
. # . # . . # # # .
. . # . . . # # # .
. # . # . . # # # .
# . . . # # . . . #
`)
img.plotImage(0)
```

### 참고 항목

[이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation), [이미지](/reference/images/image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image)