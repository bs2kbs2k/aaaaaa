# 가속도 센서 감지 값 설정

@boardname@ 의[가속도 센서 감지 값](/reference/input/acceleration) 을 설정합니다. 설정한 속도변화(가속도)를 감지하려는 경우에 사용합니다.

```sig
input.setAccelerometerRange(AcceleratorRange.OneG);
```

## 매개 변수

* `기준값`. 측정하려고 하는 기준 가속도 값. (`1g`, `2g`, `4g`, `8g`) 설정한 기준값보다 더 큰 값은 @boardname@ 를 통해 감지되지 않게 됩니다. 감지 기준값을 설정하는 경우 뿐만 아니라, 가속도를 측정하는 경우에도 적용됩니다.

## 예시

다음은 @boardname@ 로 감지할 가속도 값을 4G로 설정하고, 좌-우 방향으로의 가속도를 출력해주는 예시 코드입니다.

```blocks
input.setAccelerometerRange(AcceleratorRange.FourG);
basic.forever(() => {
    basic.showNumber(input.acceleration(Dimension.X));
});
```

### ~hint

이 프로그램은 시뮬레이터에서는 정상적으로 동작하지 않습니다. @boardname@ 에서 동작합니다.

### ~

## 참고 항목

[compass heading](/reference/input/compass-heading), [light level](/reference/input/light-level)