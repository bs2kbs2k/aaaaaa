# 온도 센서 온도

주변의 온도를 측정해보세요. 섭씨 단위로 온도가 측정됩니다. @boardname@ 에 장치된 부품의 온도를 측정해, 주변 온도를 근사적으로 측정할 수 있습니다.

```sig
input.temperature();
```

### 리턴값

* a [Number](/reference/types/number) that means the Celsius temperature.

### 어떻게 동작하나요?

@boardname@ 에 장치되어있는 CPU(중앙 처리 장치)의 온도를 측정합니다. 일반적인 상황에서는 @boardname@ 가 뜨거워지지 않습니다. 그렇기 때문에 CPU의 온도는 마이크로비트 주변의 온도와 거의 비슷합니다. 하지만, @boardname@ 로 짧은 시간에 아주 많은 작업을 실행시키는 경우에는 온도가 약간 더 올라갈 수도 있습니다!

### 예시: @boardname@ 온도계

다음은 `온도 센서 온도` 와 `정수 출력` 을 사용해 방 안의 온도를 출력해주는 예시 코드입니다.

```blocks
basic.forever(() => {
    let temp = input.temperature()
    basic.showNumber(temp)
})
```

### 예시: 화씨 온도계

다음은 화씨 온도를 측정하는 프로그램입니다. 화씨는 온도를 나타내는 다른 방법으로서 미국에서 주로 사용되는 단위입니다. 섭씨 온도를 화씨 온도로 변환하려면, 섭씨 온도에 `18` 을 곱한 후, `10` 으로 나누고, 그 값에 32 를 더하면 됩니다.

```blocks
basic.forever(() => {
    let c = input.temperature()
    let f = (c * 18) / 10 + 32
    basic.showNumber(f)
})
```

### ~hint

@boardname@ 로 측정한 온도와 실제 온도계로 측정한 온도를 서로 비교해보세요. 실제 온도계로 측정한 온도와 @boardname@ 로 측정한 온도 사이에 얼마나 차이가 나는지 살펴볼 수 있습니다. 그 차이를 프로그램에 적용시켜, 보다 정확한 온도를 측정할 수 있도록 바꿀 수 있습니다.

### ~

### 참고 항목

[자기(나침반) 센서 각도](/reference/input/compass-heading), [가속도 센서 가속도](/reference/input/acceleration)