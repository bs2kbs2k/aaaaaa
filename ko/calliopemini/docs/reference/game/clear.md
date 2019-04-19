# 이미지 지우기

이미지들을 위한 지우기 함수입니다.

[이미지](/reference/images/image) 의 모든 픽셀들을 끕니다.

### 자바스크립트

```sig
export function clear(img: micro_bit.Image)
```

### 매개 변수

* 없음

### 예시

다음은 A 버튼을 눌렀을 때, `img` 의 모든 픽셀들을 끄는 예시 코드입니다.

```blocks
let img = images.createImage(`
. . . . .
. # # # .
. # # # .
. # # # .
. . . . .
`)
img.showImage(0)
input.onButtonPressed(Button.A, () => {
    img.clear()
    img.showImage(0)
})
```

### 참고 항목

[이미지](/reference/images/image), [애니메이션 출력](/reference/basic/show-animation), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image), [이미지 만들기](/reference/images/create-image)