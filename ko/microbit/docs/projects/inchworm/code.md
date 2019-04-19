# 코드 만들기

## @description 자벌레 로봇을 살아있는 것처럼 만드는 코드

## ~avatar avatar

자벌레 로봇을 움직이게 만드는 코드를 추가하세요.

## ~

## 활동 소요시간: ~30분

## 단계 1: 계속 움직이게 만들기

자벌레 로봇을 움직이기 위해서 @boardname@ 를 이용해, 서보 모터를 `0` 도부터 `180` 도까지 회전하도록 만들어야 합니다. 다음 코드에서 **A** 버튼을 누르면 자벌레가 움직이기 시작합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    pins.servoWritePin(AnalogPin.P0, 0);
    basic.pause(500);
    pins.servoWritePin(AnalogPin.P0, 180);
    basic.pause(500);
});
```

## ~ hint

자벌레가 매우 느리게 움직이거나 전혀 움직이지 않을 수 있습니다. 다리와 이빨의 디자인을 개선해 최대한 빠르게 움직이도록 해보세요. 또한, 카페트 위에서도 미끄러지지 않고 더 잘 움직이도록 해보세요.

## ~

## ~button /projects/inchworm/connect

NEXT: 연결하기

## ~