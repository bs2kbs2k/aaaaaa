# Timing Gates

## ~avatar

이 프로젝트에서는 집에서 쉽게 볼 수 있는 물건들을 이용해, 시간 측정 게이트의 원리를 원리를 배울 수 있습니다.

## ~

## 시간 측정 게이트

Two gates are connected to the @boardname@ so it can detect a car passing through them.

![](/static/mb/projects/timing-gates/sketchgates.jpg "Sketch of the gates")

As the car passes through the gate `0`, it sends an event to the @boardname@ through the [`||pins:on pin pressed||`](/reference/input/on-pin-pressed) block. @boardname@ 보드는 그 시간을 `t0` 변수에 저장합니다.

![](/static/mb/projects/timing-gates/sketchgate1.jpg "Sketch first gate")

As the car passes through the gate `1`, it sends an event to the @boardname@ through the [`||pins:on pin pressed||`](/reference/input/on-pin-pressed) block. @boardname@ 보드는 그 시간을 `t1` 변수에 저장합니다.

![](/static/mb/projects/timing-gates/sketchgate2.jpg "Sketch first gate")

남은 것은 간단한 수학과 물리학적 계산입니다. 두 개의 시간 측정 게이트를 통과하는데 걸린 시간은 `t1 - t0` 입니다. 두 개의 게이트 사이의 거리를 두 게이트를 통과하는데 걸린 시간으로 나누면, 자동차의 속력을 구할 수 있습니다!

![](/static/mb/projects/timing-gates/sketchmath.jpg "Sketch math")

## 시간 측정 게이트 만들기 준비물

* 판지
* Aluminum foil
* 양면 테이프 (카페트 테이프)
* 악어 집게 4개
* @boardname@ 1개와 USB 케이블

![](/static/mb/projects/timing-gates/materials.jpg "Materials")

## 시간 측정 게이트 블록

```cards
basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
input.onPinPressed(TouchPin.P0, () => {})
let t = 0
input.runningTime()
t - 1
control.eventTimestamp();
basic.showNumber(0)
```

## 시간 측정 게이트 만들기

The sensor is made by tapping two strips of foil on the cardboard as close as possible.

판지에 양면 테이프를 붙이고, 보호 필름을 제거합니다.

![](/static/mb/projects/timing-gates/tape.jpg "Double sided tape")

양면 테이프 위에 알루미늄 호일을 덮습니다. 양면 테이프에 알루미늄 호일이 단단히 잘 붙도록 눌러 붙입니다.

![](/static/mb/projects/timing-gates/stickfoil.jpg "Foil sensor")

Pull off the foil that's not touching the tape strips. That's all the foil in between and around the tape strips. This clears out the extra foil and makes a gap between the foil on the tape strips. Make sure the gap is just enough so that both foil strips don't touch each other.

![](/static/mb/projects/timing-gates/spreadfoil.jpg "Foil taped")

악어 집게를 이용해 두 장의 호일에 각각 연결시킵니다.

![](/static/mb/projects/timing-gates/connectsensor.jpg "Connecting sensor")

악어 집게 한 개를 @boardname@ 의 `GND` 핀에 연결하고, 다른 악어 집게 한 개를 `P0` 핀에 연결시킵니다.

![](/static/mb/projects/timing-gates/connectcrocs.jpg "Connecting the @boardname@")

시간 측정 게이트가 준비되었습니다! 만든 결과물은 다음과 같을 것입니다.:

![](/static/mb/projects/timing-gates/sensordone.jpg "A single gate")

## 시간 측정 게이트 자동차 감지 코드

The @boardname@ provides an event [`||pins:on pin pressed||`](/reference/input/on-pin-pressed) that is raised when a circuit between `GND` and a pin is detected. 회로를 연결시켜 전기를 흘려주는 도체는 전선도 가능하고 여러분의 몸도 가능합니다! 우리는 장난감 자동차 바닥에 알루미늄 호일을 붙일 것입니다. When it passes over the gate, it connects both foil strips, closes the circuit and triggers the event.

[코드 편집기](/) 를 실행시켜 새 프로젝트를 만든 후, 다음과 같은 블록을 추가해 보세요. 여기에서는 `P0` 핀을 사용합니다.

```blocks
basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
input.onPinPressed(TouchPin.P0, () => {
    basic.showLeds(`
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        `)
})
```

Testing the code with our finger, we see a LED column turn on when pressing on both strips.

https://youtu.be/zi_-NAmdDpY

## 자동차 업그레이드하기

이 레슨에서는, 아무 장난감 자동차를 사용해서 그 바닥에 호일 조각을 붙였습니다. 그 장난감 자동차가 시간 측정 게이트를 통과하면, 양쪽 호일을 연결시켜 전기가 흐르면서 이벤트가 발생하게 됩니다. 자동차 바닥에 부착한 호일 조각이, 판지에 붙어있는 호일 조각들과 잘 연결되도록 해야합니다.

![](/static/mb/projects/timing-gates/carfoil.jpg "Attaching foil to the car")

장난감 자동차를 (천천히) 시간 측정 게이트로 통과시키면, `핀 연결되면 실행` 이벤트 블록이 실행되는 것을 확인할 수 있습니다.

https://youtu.be/M3DIUvDPlIA

## ~hint

It doesn't always work! Why? Sometimes the foil doesn't touch both strips for long enough time to be detected. This is due to the poor quality of our sensor. To fix this, you would need to use better a sensor, maybe an IR detector or a Hall effect sensor.

## ~

## 두 번째 시간 측정 게이트 추가하기

첫 번째 시간 측정 게이트를 만들었던 것과 똑같은 방법으로, 두 번째 시간 측정 게이트를 만듭니다.

![](/static/mb/projects/timing-gates/sensor2.jpg "Double foil sensors")

악어 집게 한 개를 @boardname@ 의 `GND` 핀에 연결하고, 다른 악어 집게 한 개를 `P1` 핀에 연결시킵니다.

![](/static/mb/projects/timing-gates/sensormicrobit2.jpg "Sensor and microbit")

## 두 번째 시간 측정 게이트 감지하기

Since the second gate is connected to pin `P1`, we add a second [`||pins:on pin pressed||`](/reference/input/on-pin-pressed) event that display 2 columns of LEDs.

```blocks
basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
input.onPinPressed(TouchPin.P0, () => {
    basic.showLeds(`
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        `)
})
input.onPinPressed(TouchPin.P1, () => {
    basic.showLeds(`
        # . . . #
        # . . . #
        # . . . #
        # . . . #
        # . . . #
        `)
})
```

2 개의 시간 측정 게이트를 연속적으로 자동차가 통과하게 되면, 첫 번째 게이트를 통과한 시간과 두 번째 게이트를 통과한 시간을 알아낼 수 있습니다.

https://youtu.be/N4bWQcu6yWs

## 시간 계산하기

@boardname@ 에는 시간을 정확히 잴 수 있는 시간 클록이 장치되어있습니다. 그 시간 클록을 사용하면 @boardname@ 에 전원이 켜진 순간부터 흐른 시간을 측정할 수 있습니다. 첫 번째 게이트를 통과한 시간은 `t0` 에 저장되고, 두 번째 게이트를 통과한 시간은 `t1` 에 저장될 것입니다. 그 두 변수 `t1`, `t0` 에 저장되어있는 시간 차이를 계산하면, 두 게이트 사이의 이동 시간을 알아낼 수 있습니다.

```blocks
let t0 = 0;
let t1 = 0;
basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
input.onPinPressed(TouchPin.P0, () => {
    t0 = control.eventTimestamp();
    basic.showLeds(`
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        # . . . .
        `)
})
input.onPinPressed(TouchPin.P1, () => {
    t1 = control.eventTimestamp();
    basic.showLeds(`
        # . . . #
        # . . . #
        # . . . #
        # . . . #
        # . . . #
        `)
    let d = t1 - t0
    basic.showNumber(d)
})
```

https://youtu.be/piyym_ux1EM

## 속도 계산하기

Measure the distance between the gates and apply Newton's laws to compute the velocity (how fast it's going) of the car.

    v = d / t
    

이 부분은 여러분의 생각과 힘으로 직접 프로그래밍 해보세요!