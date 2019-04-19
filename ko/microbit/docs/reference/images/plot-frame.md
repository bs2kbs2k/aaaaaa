# 프레임 출력

프레임 출력 함수.

[이미지](/reference/images/image) 를 @boardname@ 의 [LED 스크린](/device/screen) 에 출력해보세요.

## 자바스크립트

```sig
export function plotFrame(_this: micro_bit.Image, index: number)
```

## 매개 변수

* 위치 - [정수](/types/number); 이미지 출력을 시작할 프레임 위치

## `이미지 출력` 과의 차이점

`프레임 출력` 함수는 프레임 번호를 사용합니다.(두 개의 프레임으로 구성되는 경우에는 0 또는 1의 번호를 사용할 수 있습니다.), 반면에 `이미지 출력` 은 시작 오프셋 위치를 사용합니다.(두 개의 프레임이 있는 경우, 시작 오프셋 위치는 0부터 9까지 가능합니다.)

## 예시

```blocks
let img = images.createImage(`
# . . . # # . . . #
. # . # . . # # # .
. . # . . . # # # .
. # . # . . # # # .
# . . . # # . . . #
`)
img.plotFrame(1)
```

## 참고 항목

[이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation), [이미지](/reference/images/image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image)