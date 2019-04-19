# LED 그래프

원하는 어떤 값을 LED 그래프 형태로 출력합니다. LED 그래프는 어떤 값과 가능한 최댓값의 비율을 이용해, 막대 그래프 형태로 표현한 것입니다.

```sig
led.plotBarGraph(2, 20);
```

### 매개 변수

* `value` is a [number](/reference/types/number) that means what you are measuring or trying to show. 예를 들어, @boardname@ 를 이용해 얼음의 온도를 측정하는 경우, `표현할 값` 은 `0` 이 됩니다. 얼음의 온도는 섭씨로 표현하는 100 단위 눈금에서 0 도 이기 때문입니다.
* `high` is a [number](/reference/types/number) that means the highest possible number that the `value` parameter can be. 최댓값은 LED 그래프가 모두 채워진 그래프 형태가 됩니다.

### 예시: 가속도 차트

다음은 [가속도](/reference/input/acceleration) 를 LED 그래프 형태로 출력해 주는 코드 예시입니다. @boardname@ 의 `x축 방향` 가속도를 출력해 줍니다. @boardname@ 의 `x축 방향` 은 왼쪽에서 오른쪽방향(또는, 오른쪽에서 왼쪽방향) 을 의미합니다. @boardname@ 를 그 방향으로 빠르게 가속시키면 시킬수록, LED 그래프 형태로 출력되는 줄들이 더 커질 것입니다. `가능한 최댓값` 으로 설정한 값이 가장 큰 값이며, LED 그래프 형태를 꽉 채워 출력하게됩니다.

```blocks
basic.forever(() => {
    let a = input.acceleration(Dimension.X);
    led.plotBarGraph(a, 1023)
})
```

### 참고 항목

[LED 스크린 밝기](/reference/led/brightness), [페이드 인](/reference/led/fade-in), [페이드 아웃](/reference/led/fade-out), [LED 스크린](/device/screen), [LED 스크린 애니메이션 중지](/reference/led/stop-animation)