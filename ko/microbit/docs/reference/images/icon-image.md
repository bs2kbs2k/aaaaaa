# 아이콘 이미지

[아이콘 이미지](/reference/images/image) 를 만들어 [LED 스크린](/device/screen) 에 출력해보세요.

```sig
images.iconImage(IconNames.Heart);
```

미리 만들어져 내장되어있는 아이콘들이 많이 있습니다. @boardname@ 의 [LED 스크린](/device/screen) 을 통해 출력해보세요. 아이콘 이름을 살펴보고 선택하면 됩니다.

## 매개 변수

* **아이콘 이름**: [LED 스크린](/device/screen) 을 통해 출력할 아이콘 이름. 다음과 같은 아이콘을 고를 수 있습니다.: `하트`.

## 예시

다음은 A 버튼을 눌렀을 때 행복함 아이콘이 출력되고, B 버튼을 누르면 슬픔 아이콘이 출력되는 예시 코드입니다.

```blocks
let iamHappy = images.iconImage(IconNames.Happy)
let iamSad = images.iconImage(IconNames.Sad)

input.onButtonPressed(Button.A, () => {
    iamHappy.showImage(0);
});
input.onButtonPressed(Button.B, () => {
    iamSad.showImage(0);
});
```

## 참고 항목

[arrow image](/reference/images/arrow-image)