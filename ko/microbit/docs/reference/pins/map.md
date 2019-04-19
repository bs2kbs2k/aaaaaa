# 값 변환(map)

어떤 범위에 있는 값을 다른 범위의 값으로 변환합니다. 이 함수는 `현재 최솟값`, `변환 최솟값`, `현재 최댓값` `변환 최댓값` 범위를 이용해, 어떤 값을 다른 범위의 비율에 맞춰 변환해줍니다.

이 함수는 값들을 어떤 범위로 제한하지 않습니다. 그렇기 때문에 그 범위를 벗어나는 다른 범위의 값들로 쉽게 바꿀 수 있습니다. 범위를 제한하고 싶은 경우에는, `Math.clamp` 등과 같은 함수를 사용하면 됩니다.

```sig
pins.map(0, 0, 4, 0, 1023);
```

## 매개 변수

* `값(value)`. 변환할 [수(정수)](/types/number)
* `현재 최솟값`. 현재 값이 가질 수 있는 최소 [수(정수)](/types/number)
* `현재 최댓값`. 현재 값이 가질 수 있는 최대 [수(정수)](/types/number)
* `변환 최솟값`. 변환된 값이 가질 수 있는 최소 [수(정수)](/types/number)
* `변환 최댓값`. 변환된 값이 가질 수 있는 최대 [수(정수)](/types/number)

## 예시

다음은 `P0` 핀에서 아날로그로 입력받은 값을, `0` 부터 `4` 범위의 LED 좌표로 변환하는 예시입니다.

```blocks
let value1 = pins.analogReadPin(AnalogPin.P0)
let index = pins.map(value1, 0, 1023, 0, 4)
led.plot(0, index)
```

## 참고 항목

[analog read pin](/reference/pins/analog-read-pin)