# 이미지 스크롤

[이미지](/reference/images/image)(사진)를 [LED 스크린](/device/screen) 에서 스크롤(슬라이드) 합니다.

```sig
let item: Image = null;
item.scrollImage(5, 200);
```

### 매개 변수

* a [number](/reference/types/number) that means how many LEDs to scroll at a time, from right to left or left to right. `2` 와 같은 양의 정수를 사용하면, 오른쪽에서 왼쪽으로 이미지가 스크롤 됩니다. `-2` 와 같은 음의 정수를 사용하면, 반대 방향으로 이미지가 스크롤 됩니다. 또한, `5` 나 `-5` 와 같은 경우, 한 번에 한 **프레임**씩 스크롤 한 것과 같은 효과가 나타납니다. (프레임은 큰 이미지를 구성하는 한 조각이라고 할 수 있습니다. LED 5개 길이의 정사각 크기 입니다.) 이러한 프레임은 **애니메이션**을 출력할 때 편리합니다.

* a [number](/reference/types/number) that means how many milliseconds to wait before scrolling the amount that `offset` says. (1000 밀리초는 1초를 의미합니다.) 수가 크면 클 수록, 느리게 스크롤 됩니다.

### 예시

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

### 참고 항목

[이미지 출력](/reference/images/show-image), [이미지](/reference/images/image), [이미지 만들기](/reference/images/create-image), [애니메이션 출력](/reference/basic/show-animation)