# 픽셀

픽셀 함수.

[이미지](/reference/images/image) 의 픽셀 상태를 읽어옵니다.

### 자바스크립트

```sig
export function pixel(_this: micro_bit.Image, x: number, y: number) : boolean
```

### 매개 변수

* x - [Number](/reference/types/number); the *x coordinate* or horizontal position of a pixel in an [image](/reference/images/image)
* y - [Number](/reference/types/number); the *y coordinate* or vertical position of a pixel in an [image](/reference/images/image)

### x, y 좌표란?

`x`, `y` 좌표에 대해서 살펴보려면, [LED 스크린](/device/screen) 을 참고해주세요.

### 리턴값

* [불 값](/blocks/logic/boolean) - 켜져있으면 `참(true)`, 꺼져있으면 `거짓(false)`

### 예시

다음은 `0, 0` 좌표에 있는 LED 의 상태를 확인하는 예시 코드입니다. `img` 이미지에 있는 픽셀 상태를 확인합니다.:

### ~hide

```blocks
let img = images.createImage(`
. . # . . . . . . .
. # . # . . . # . .
. . # . . . . . . .
. # . # . . . # . .
. . # . . . . . . .
`)
```

### ~

```typescript-ignore
let state = img.pixel(0, 0)
```

### 참고 항목

[LED 설정](/reference/images/set-pixel), [이미지 출력](/reference/images/show-image), [이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [이미지 스크롤](/reference/images/scroll-image)