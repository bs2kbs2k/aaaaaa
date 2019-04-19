# 화살표 이미지

화살표 모양의 [이미지](/reference/images/image) 를 [LED 스크린](/device/screen) 에 출력해보세요.

```sig
images.arrowImage(ArrowNames.North)
```

선택한 방향으로 화살표 방향이 표시됩니다. 예시 `북쪽`.

## 매개 변수

* **화살표이름**: 화살표 [이미지](/reference/images/image) 의 방향을 의미하는 화살표 이름. 다음과 같은 방향이름 사용가능:

> * `북쪽`

* `북동쪽`
* `동쪽`
* `남동쪽`
* `남쪽`
* `남서쪽`
* `서쪽`
* `북서쪽`

## 예시

다음은 A 버튼을 누르면 왼쪽 방향의 화살표가 출력되고, B 버튼을 누르면 오른쪽 방향의 화살표가 출력되는 예시 코드입니다.

```blocks
let arrowLeft = images.arrowImage(ArrowNames.West)
let arrowRight = images.arrowImage(ArrowNames.East)

input.onButtonPressed(Button.A, () => {
    arrowLeft.showImage(0);
});
input.onButtonPressed(Button.B, () => {
    arrowRight.showImage(0);
});
```

## 참고 항목

[arrow number](/reference/images/arrow-number)