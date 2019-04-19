# 이미지

LED 스크린을 통해 출력하고, 스크롤 할 수 있는 이미지를 만들 수 있습니다.

```cards
images.createImage(`
. . . . .
. . . . .
. . # . .
. . . . .
. . . . .
`);
images.createBigImage(`
. . . . .
. . . . .
. . # . .
. . . . .
. . . . .
`);
images.createImage(``).showImage(0);
images.createImage(``).scrollImage(0,0);
images.arrowImage(ArrowNames.North)
images.iconImage(IconNames.Heart)
images.arrowNumber(ArrowNames.North)
```

## 참고 항목

[이미지 만들기](/reference/images/create-image), [큰 이미지 만들기](/reference/images/create-big-image), [이미지 출력](/reference/images/show-image), [이미지 스크롤](/reference/images/scroll-image), [화살표 이미지](/reference/images/arrow-image), [아이콘 이미지](/reference/images/icon-image), [화살표 번호](/reference/images/arrow-number)