# @extends

## 시작하기 전에... #setup

다음 안내를 따라 @boardname@ 를 준비합니다. [시리얼통신 연결 설정하기](/device/serial).

## 일반적인 시나리오 #example

일반적인 상황에서는 센서 데이터를 그래프로 그린 후, 편집기에서 분석할 수 있습니다. 예를 들어, 다음 코드를 @boardname@ 에서 실행시켜보세요.

```blocks
basic.forever(() => {
   led.plotBarGraph(input.acceleration(Dimension.X), 0);
});
```

시리얼통신이 정상적으로 동작하는 경우, @boardname@ 를 통해 감지된 `x` 축 방향 가속도들이 그래프 차트로 그려지는 것을 확인할 수 있습니다. `LED 그래프` 함수가 호출될 때마다, 동시에 그 값을 시리얼통신으로 출력합니다. 데이터가 기록 로그가 자동으로 보여지는 것으로서, 전달되는 데이터 스트림을 그래프 형태로 표현하는 것입니다.