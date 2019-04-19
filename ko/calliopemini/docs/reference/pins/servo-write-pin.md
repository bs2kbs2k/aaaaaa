# 서보 출력

[핀](/device/pins) 에 연결된 서보 모터에 값을 출력해서, 서보 모터의 회전축을 제어합니다.

일반 서보 모터의 경우에는 회전 각도를 제어할 수 있으며, 무한회전 서보 모터의 경우에는 회전 속도를 제어할 수 있습니다. (`0` 인 경우 정방향 최고 회전 속도, `180` 인 경우 역방향 최고 회전 속도, 약 `90` 인 경우 움직이지 않는 중립 상태)

```sig
pins.servoWritePin(AnalogPin.P1, 180)
```

### 매개 변수

* `name`: a [string](/reference/types/string) that specifies the pin name (`P0` through `P4`, or `P10`)
* `value`: a [number](/reference/types/number) from `0` through `180`

### 예시

#### 서보 모터의 회전축 각도를 중간으로 만들기

```blocks
pins.servoWritePin(AnalogPin.P1, 90)
```

#### 가속도 센서를 통해 얻은 기울기 값을, 서보 모터의 회전축 각도로 만들기

```blocks
basic.forever(() => {
    let millig = input.acceleration(Dimension.X)
    // map accelerometer readings to angle
    let angle = pins.map(millig, -1023, 1023, 0, 180)
    pins.servoWritePin(AnalogPin.P1, angle)
})
```

#### 무한회전 서보 모터의 회전 속도를 가장 빠르게 만들기

```blocks
pins.servoWritePin(AnalogPin.P1, 0)
```

### 참고 항목

[@boardname@ 핀](/device/pins), [서보 출력 설정 주기](/reference/pins/servo-set-pulse)