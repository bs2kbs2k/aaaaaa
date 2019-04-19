# LED 픽셀 설정

LED 픽셀을 설정합니다. #set pixel.

[이미지](/reference/images/image) 를 구성하는 LED 상태를 설정해 켜고 끌 수 있습니다.

### 자바스크립트

```sig
export function setPixel(_this: micro_bit.Image, x: number, y: number, value: boolean)
```

### 매개 변수

* x - [Number](/reference/types/number); the *x coordinate* or horizontal position of a pixel in an [image](/reference/images/image)
* x - [Number](/reference/types/number); the *y coordinate* or vertical position of a pixel in an [image](/reference/images/image)
* 값 -[불 값](/blocks/logic/boolean); LED 픽셀의 on/off 상태; 켬 `참(true)`, 끔 `거짓(false)`

### x, y 좌표란?

`x`, `y` 좌표에 대해서 살펴보려면, [LED 스크린](/device/screen) 을 참고해주세요.

### 예시

다음은 이미지를 만들고, 그 이미지를 `img` 변수에 저장하는 코드 예시입니다. `LED 픽셀 설정` 함수를 이용해 가운데 LED 픽셀을 끕니다. 그 앞에서 `img` 에 저장된 이미지를 `이미지 출력` 함수를 이용해 출력합니다.

```blocks
let img = images.createImage(`
. . # . .
. # . # .
. . # . .
. # . # .
. . # . .
`)
img.setPixel(2, 2, false)
img.showImage(0)
```

### 참고 항목

[LED 설정](/reference/images/pixel), [이미지 출력](/reference/images/show-image), [이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [이미지 스크롤](/reference/images/scroll-image)