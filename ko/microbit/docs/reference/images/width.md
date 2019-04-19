# 이미지 너비

이미지 너비(폭, 좌우 길이) 계산 함수.

[이미지](/reference/images/image) 의 너비(좌우 길이)를 얻어낼 수 있습니다.

```sig
images.createImage().width();
```

## 리턴값

* [정수](/types/number) - 이미지의 너비(가로 길이, 폭) 크기. 이미지가 한 프레임(5*5)인 경우 5, 두 프레임인 경우 10, 세 프레임인 경우 15, ... 를 리턴합니다. 이미지의 가로 크기를 알아낸 후, 그 값을 5 로 나누면, 몇 개의 프레임으로 구성되어있는지 알 수 있습니다.(아래 코드를 살펴보세요)

다음은 `img` 의 가로 크기를 알아낸 후, 그 크기를 `w` 변수에 저장해 사용하는 코드 예시입니다:

## ~hide

```blocks
let img = images.createImage(`
. . # . . . . . . .
. # . # . . . # . .
. . # . . . . . . .
. # . # . . . # . .
. . # . . . . . . .
`)
```

## ~

```typescript-ignore
let w = img.width()
```

## 예시: 프레임별로 출력하기

다음은 `이미지 너비` 함수와 [반복(for)](/blocks/loops/for) 구조를 이용해, 이미지 프레임의 개수를 스크린에 출력하는 코드 예시입니다.:

```typescript
let img2 = images.createImage(`
. . # . . . # # # # . # # # .
. # # . . . . . . # . . . # .
. . # . . . . . # . . . # . .
. . # . . . . # . . . . . # .
. . # . . . # # # # . # # # .
`)
for (let i = 0; i < img2.width() / 5; i++) {
    img2.showImage(i * 5)
    basic.pause(1000)
}
```

## 참고 항목

[이미지 출력](/reference/images/show-image), [이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [이미지 스크롤](/reference/images/scroll-image), [애니메이션 출력](/reference/basic/show-animation)