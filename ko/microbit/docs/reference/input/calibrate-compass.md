# 자기(나침반) 센서 보정

자기(나침반) 센서 보정 과정을 실행합니다.

```sig
input.calibrateCompass();
```

## 보정(Calibration)

보정 과정에서 @boardname@ 를 돌려 원을 그리거나 기울여 LED 스크린의 불빛을 채우게 됩니다.

자기(나침반) 센서를 보정하거나 사용할 때, 주변에 금속 물체가 있는 경우, @boardname@ 에 간섭을 일으킬 수 있습니다.

## 예시

다음은 **A+B** 버튼을 눌렀을 때, 자기(나침반) 센서 보정을 실행하는 예시입니다.

```blocks
input.onButtonPressed(Button.AB, () => {
    input.calibrateCompass();
})
```

## 참고 항목

[자기(나침반) 센서 각도](/reference/input/compass-heading)