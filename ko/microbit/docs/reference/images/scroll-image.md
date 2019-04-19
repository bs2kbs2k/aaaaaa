# 이미지 스크롤

[이미지](/reference/images/image)(사진)를 [LED 스크린](/device/screen) 에서 스크롤(슬라이드) 합니다.

```sig
let item: Image = null;
item.scrollImage(5, 200);
```

## 매개 변수

* a [number](/types/number) that means how many LEDs to scroll at a time from right to left. You must use a positive number like `2`. If you use `5`, the image will scroll one **frame** at a time. (A frame is a part of the image. It is a square with five LEDs on a side). This is useful for **animation**.

* [정수](/types/number). 오프셋 시작번호 프레임을 처음 출력할 때까지 걸리는 밀리초. `오프셋`은 처음 출력하는 프레임 번호라고 할 수 있습니다. (1000 밀리초는 1초를 의미합니다.) 수가 크면 클 수록, 느리게 스크롤 됩니다.

## 예시

다음은 두 가지 화살표 이미지를 포함하고 있는 큰 이미지를 스크롤 하는 예시로서, 이미지 스크롤 시간 간격을 200 밀리초로 설정한 예시 코드입니다. 이미지 프레임은 LED 5개 크기이기 때문에, 북쪽-남쪽 방향 화살표가 위 아래로 번갈아 바뀌는 애니메이션처럼 보여지게 됩니다. 물론, 화살표 이미지 뿐만 아니라 다른 것을 나타내는 프레임도 사용할 수 있습니다.

```blocks
let arrows = images.createBigImage(`
    . . # . .   . . # . .
    . # # # .   . . # . .
    # . # . #   # . # . #
    . . # . .   . # # # .
    . . # . .   . . # . .
    `);
basic.forever(() => {
    arrows.scrollImage(5, 200);
}); 
```

## 참고 항목

[이미지 출력](/reference/images/show-image), [이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation)