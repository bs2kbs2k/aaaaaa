# 이미지

@boardname@ 스크린용 이미지

## @parent blocks/language

*이미지* 는 [LED 스크린](/device/screen) 으로 출력시킬 픽셀 행렬(배열) 입니다.

## 블록 편집기: LED 출력

이미지를 출력하기 위해서는:

* `기본`, `LED 출력` 을 순서대로 누른 후, 원하는 LED 들을 클릭하면 됩니다.

```blocks
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
```

## 이미지 만들기

나중에 수정할 수 있는 이미지를 만들려면 [이미지 만들기](/reference/images/create-image) 함수를 살펴보세요.

1. 왼쪽의 **이미지** 카테고리를 클릭하세요.

2. **이미지 출력** 블록을 가져온 후, 작성하고 있는 프로그램 코드에 넣으세요.

3. **이미지 만들기** 나 **큰 이미지 만들기** 블록을 **이미지 출력** 블록 안에 넣고 연결시키세요.

4. **이미지 만들기** 블록 안에 있는 작은 사각형들을 클릭해 이미지를 만드세요.

다음과 비슷한 코드를 만들 수 있을 것입니다.:

![](/static/mb/blocks/image-0.png)

## 이미지 함수

* [이미지 만들기](/reference/images/create-image): LED 들을 켜고 꺼서 이미지를 만들 수 있습니다.
* [LED 스크린 지우기](/reference/basic/clear-screen): 이미지를 나타내는 모든 픽셀을 끕니다.
* [LED 상태](/reference/images/pixel): 이미지를 만드는 특정 픽셀의 상태를 읽어옵니다.
* [LED 출력](/reference/basic/show-leds): 한 프레임의 이미지를 LED 스크린에 출력합니다.
* [이미지 출력](/reference/images/show-image): 스크린에 이미지를 출력합니다.
* [이미지 스크롤](/reference/images/scroll-image): 스크린에 이미지를 스크롤합니다.

## 참고 항목

[LED 출력](/reference/basic/show-leds), [이미지 만들기](/reference/images/create-image), [이미지 출력](/reference/images/show-image), [LED 스크린](/device/screen)