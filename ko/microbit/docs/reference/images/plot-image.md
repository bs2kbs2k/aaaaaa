# 이미지 플로트

이미지 플로트 함수.

[이미지](/reference/images/image) 를 @boardname@ 의 [LED 스크린](/device/screen) 에 출력해보세요.

## 자바스크립트

```sig
export function plotImage(_this: micro_bit.Image, xOffset: number)
```

## 매개 변수

* x 오프셋(시작위치) - [정수](/types/number); 이미지출력 시작위치; 0 은 이미지의 첫 번째 프레임을 의미하고, 5 는 이미지의 두 번째 프레임을 의미합니다. 10은 세 번째 프레임...

## `이미지 출력` 과의 차이점

`이미지 출력` 함수는 400 밀리초가 지나야 다음 이미지를 출력하는 반면, `이미지 플로트` 는 그러한 시간 지연이 없습니다.

## 예시

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

## 참고 항목

[이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation), [이미지](/reference/images/image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image)