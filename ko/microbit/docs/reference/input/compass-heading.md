# 자기(나침반) 센서 각도

@boardname@ 보드가 향하고 있는 방향을 알아냅니다.

The @boardname@ measures the **compass heading** from `0` to `359` degrees with its **magnetometer** chip. 그 값은 보드가 향하고 있는 북, 동, 남, 서 방향을 나타낸 것입니다.

```sig
input.compassHeading();
```

## 리턴값

* a [number](/types/number) from `0` to `359` degrees, which means the compass heading. If the compass isn't ready, it returns `-1003`.

## 예시

다음 코드는 자기(나침반) 센서가 가리키는 북쪽 방향 각도를 측정해, `degrees` 변수에 저장합니다.

```blocks
let degrees = input.compassHeading()
```

## ~hint

이 함수를 웹브라우저에서 실행시키면, 시뮬레이터 화면에 나타나는 나침반 바늘을 드래그 앤 드롭해서 나침반 북쪽 방향을 바꿔볼 수 있습니다.

## ~

## 예시: 나침반

다음 코드는 자기(나친반) 센서를 이용해 북쪽 방향을 찾고, 측정된 방향을 @boardname@ 를 통해 북(N), 남(S), 동(E), 서(W)로 출력해 보여주는 예시입니다.

```blocks
let degrees = 0
basic.forever(() => {
    degrees = input.compassHeading()
    if (degrees < 45) {
        basic.showArrow(ArrowNames.North)
    } else if (degrees < 135) {
        basic.showArrow(ArrowNames.East)
    } else if (degrees < 225) {
        basic.showArrow(ArrowNames.South)
    } else if (degrees < 315) {
        basic.showArrow(ArrowNames.West)
    } else {
        basic.showArrow(ArrowNames.North)
    }
})
```

## 보정(Calibration)

자기(나침반) 센서를 사용하는 경우(예를 들어, 나침반 센서 기능을 동작시키는 경우), @boardname@ 보드는 [자기(나침반) 센서 보정](/reference/input/calibrate-compass) 을 시작할 것입니다.(자체 보정) 그 과정에서 @boardname@ 를 기울여 원을 그리도록 요청할 것입니다.

자기(나침반) 센서를 보정하거나 사용할 때, 주변에 금속 물체가 있는 경우, @boardname@ 에 간섭을 일으킬 수 있습니다.

## ~ hint

다음 코드는 **A+B** 를 눌러 자기(나침반) 센서 보정을 실행하도록 하는 예시입니다.

```block
input.onButtonPressed(Button.AB, () => {
    input.calibrateCompass();
})
```

## ~

## 참고 항목

[가속도](/reference/input/acceleration), [자기(나침반) 센서 보정](/reference/input/calibrate-compass)