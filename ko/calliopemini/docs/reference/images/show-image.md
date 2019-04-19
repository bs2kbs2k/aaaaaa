# 이미지 출력

[이미지](/reference/images/image)(사진)를 [LED 스크린](/device/screen) 에 출력해보세요. @boardname@ 에서 이미지가 출력된 후, 400 밀리초(1초는 1000 밀리초) 동안 일시 중지 됩니다.

```sig
let item: Image = null;
item.showImage(0);
```

### 매개 변수

* [이미지](/reference/images/image) (사진). LED 가로 5칸, 세로 5 칸 크기의 이미지 또는 그 보다 넓은 가로 길이의 이미지. 
* a [number](/reference/types/number) that says how many LEDs from the left of the picture the @boardname@ should start. `0` 은 그림의 첫 번째 **프레임** 부터 출력하는 것을 의미하며, `5` 는 두 번째 프레임부터 출력, `10` 은 세 번째 프레임부터 ...

### 예시: 화살표 뒤집기

다음은 북쪽 화살표 프레임과 남쪽 화살표 프레임을 이어 붙인 것과 같은 큰 이미지를 만드는 예시 코드입니다. `A` 버튼을 누르면, `이미지 출력` 함수가 실행되어 북쪽 화살표가 출력됩니다. (큰 이미지의 가장 왼쪽에 있는 LED 좌표는 `0` 입니다.) `B` 버튼을 누르면, `이미지 출력` 함수가 실행되어 남쪽 화살표가 출력될 것입니다. 남쪽 화살표 부분은 `5` 번째 세로줄 부터 시작됩니다.

```blocks
let arrows = images.createBigImage(`
    . . # . .   . . # . .
    . # # # .   . . # . .
    # . # . #   # . # . #
    . . # . .   . # # # .
    . . # . .   . . # . .
    `);
input.onButtonPressed(Button.A, () => {
    arrows.showImage(0);
});
input.onButtonPressed(Button.B, () => {
    arrows.showImage(5);
});
```

### 참고 항목

[Getting Started](/getting-started), [image](/reference/images/image), [create image](/reference/images/create-image), [create big image](/reference/images/create-big-image), [scroll image](/reference/images/scroll-image), [show animation](/reference/basic/show-animation)