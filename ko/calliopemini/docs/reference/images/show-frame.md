# 프레임 출력

프레임 출력 함수.

[이미지](/reference/images/image) 를 @boardname@ 의 [LED 스크린](/device/screen) 에 출력해보세요.

### 자바스크립트

```sig
export function showFrame(img: micro_bit.Image, frame: number)
```

### 매개 변수

* index - [Number](/reference/types/number); which frame of the image to display

### `프레임 플로트` 와의 차이점

`프레임 출력` 함수는 [프레임 플로트](/reference/images/plot-frame) 함수와 같습니다. 하지만, LED 스크린이 갱신되는 기본 화면 갱신 대기 시간이 있습니다.(반면에 `프레임 플로트` 는 화면 갱신 대기 시간이 없습니다.)

### 예시

```blocks
let img = images.createImage(`
# . . . # # . . . #
. # . # . . # # # .
. . # . . . # # # .
. # . # . . # # # .
# . . . # # . . . #
`)
img.showFrame(1)
```

### 참고 항목

[이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation), [이미지](/reference/images/image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image)