# 반응 시간 실험장치 코드 만들기

## @description 반응 시간 측정 실험 장치를 위한 코드

이 레슨은 @boardname@ 를 이용해 학생들의 반응 시간을 측정합니다. 판지에 붙이 패드를 통해 전기를 흐르게 만드는 방법으로 시간을 측정합니다. 학생들의 반응 시간은 시끄러운 상황에서 측정하고, 다시 조용한 상황에서 측정해 비교해 볼 수도 있습니다.

알루미늄 호일 조각을 @boardname@ 의 적절한 핀에 각각 연결시키세요.

**참고:** 실험에서는 동영상에서 보이는 것과 같은 핀을 **사용하지 않습니다.** **P2** 핀을 사용하지 않습니다.

한 손을 접지 핀과 연결된 부분에 대고 (**GND**), 다른 한 손을 **P0** 핀에 대는 방법으로 반응 시간을 측정할 수 있습니다. 그렇게 하면, 기본 3 초의 카운트다운 시간이 흐른후, @boardname@ 의 전기 회로를 연결하는 방법으로 시간을 측정할 수 있습니다.

타이머가 시작되면, 한 손을 **GND** 핀과 연결된 호일 조각에 대고 있는 상태에서 LED 스크린에 불이 켜지는 것을 기다렸다가, 다른 손으로 **P1** 핀에 연결된 호일 조각을 만지면 됩니다. 그렇게 하면 전기 회로가 연결되고, 타이머를 중지시킬 것입니다.

그렇게 되면, @boardname@ 으로 그 시간 간격을 측정할 수 있습니다. 타이머가 시작된 후, 전기 회로가 연결될 때까지 걸린 시간을 측정할 수 있는 것입니다.

## 단계 1: 변수 만들기

**반응 시간 측정** 실험을 위해서는 사람의 반응 속도를 측정하기 위한 방법을 만들고 따라가야 합니다. 시간 데이터를 기록하기 위한 변수들을 만들어야 합니다. 변수들을 사용하기 전에, 변수들을 초기화(저장 또는 설정)시켜 어떤 값을 저장해 두는 것이 좋습니다. 필요한 변수들은 다음과 같습니다.: `start`, `end`, `false_start`, `running`. 변수들의 값을 `start` 와 `end` 를 `0` 으로 설정합니다. 0 은 시간이 흐르지 않았다는 것을 의미합니다. 그 다음에 변수들의 값을 다음과 같이 설정합니다. `false_start` 와 `running` 을 `거짓(false)` 으로 설정합니다. 아직 시작되지 않았다는 것을 의미합니다.

다음 코드에서는 변수들에 저장되는 값들을 추적합니다.: - 사람의 반응에 따라 시간 측정이 시작되고 끝나는, 반응 시간 측정 실험이 가능하도록 할 것입니다. - 반응 시간 측정 실험에서는, 반응 시간 측정 시작 전에 미리 반응하는 부정 시작의 경우도 판단할 수 있습니다.

이러한 변수들을 코드에 추가합니다.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
running = false
false_start = false
end = 0
start = 0
```

## 단계 2: 핀 연결되면 실행

한 손은 **GND** 핀에 대고, 다른 한 손은 **P0** 이나 **P1** 에 연결되어 회로에 전기가 흐를 때, 실행시킬 이벤트 처리기를 등록해야 합니다. 2 개의 `||input:on pin pressed||` 블록이 필요합니다. 각각**P0** 과 **P1** 용입니다.

`||input:on pin pressed||` 블록들을 코드에 추가합니다.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {

})
input.onPinPressed(TouchPin.P1, () => {

})
running = false
false_start = false
end = 0
start = 0
```

## 단계 3: 카운트다운 타이머

**P0** 핀이 연결되었을 때 카운트다운 시간을 표시하기 위해서, 카운트다운 타이머가 필요합니다. 3 개의 `||basic:show number||` 블록을 이용해 카운트다운 숫자가 순서대로 보여질 수 있도록 합니다.: **3**...**2**...**1**. 화면에서 숫자를 지우려면, `||basic:clear screen||` 블록이 필요합니다. 코드를 수정해 다음과 같이 만들어보세요:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
})
input.onPinPressed(TouchPin.P1, () => {

})
running = false
false_start = false
end = 0
start = 0
```

## 단계 4: 불 값

이제 `running`, `false_start` 변수 값을 `거짓(false)` 으로 만듭니다. **P0** 이 연결되는 이벤트에 대해서 처리하면 됩니다.

`||variables:set to||`블록들을 `실행` 시키기 위해서 추가하고, `false_start` 변수 값을 다음과 같이 설정해 둡니다.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
})
input.onPinPressed(TouchPin.P1, () => {

})
running = false
false_start = false
end = 0
start = 0
```

## 단계 5: 반응 시간 측정 랜덤으로 시작하기

**p0** 핀이 연결되었을 때, 랜덤으로 시작하도록 추가해봅시다. 이벤트 블록의 마지막 부분에 다음과 같이, `||math:random||` 블록을 `||basic:pause||` 안에 넣습니다.

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
})
input.onPinPressed(TouchPin.P1, () => {

})
running = false
false_start = false
end = 0
start = 0
```

## 단계 6: LED 좌표 랜덤으로 뽑아 켜기

부정 시작(false start)(**P0** 핀이 허용된 시간에 눌리지 않은 경우)이 아닌 경우에만 반응 시간을 측정해야합니다. 반응 시간 측정이 시작되면, 임의의 LED 가 화면의 랜덤 위치에 나타납니다. 반응 시간을 보여줄 수 있도록 `||logic:if then||` 블록에 추가합니다.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P1, () => {

})
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
    if (!(false_start)) {
        start = input.runningTime()
        running = true
        led.stopAnimation()
        basic.clearScreen()
        led.plot(Math.random(5), Math.random(5))
    }
})
running = false
false_start = false
end = 0
start = 0
```

## 단계 7: 반응 시간 출력하기

한 손으로 **GND** 핀에 연결된 호일을 잡고, 다른 한 손으로 **P1** 핀에 연결된 호일에 손을 댔을 때를 감지하기 위해 코드를 추가합니다. 그렇게 하면 전기 회로가 연결되고, 타이머를 중지시킬 것입니다. 또한, @boardname@ 에서 타이머가 시작된 시간부터 회로가 연결될 때까지의 시간 차이를, 밀리초 단위로 읽어오는 코드를 만들어야 합니다. 이 코드는 **P1** 핀이 연결되었는지를 검사해서, 부정 측정인지 아닌지도 검사해야 합니다.

**P1** 핀이 연결되면 두 이미지 중 한 가지를 출력하도록 해봅시다. 첫 번째 이미지는 **GND** 와 **P**1 핀을 연결시켜 정상적으로 반응 시간을 측정했을 때의 이미지입니다. 랜덤으로 LED 가 켜진후 **P1** 핀과 연결된 회로에 전기가 흐르면, 반응 시간을 정상적으로 체크한 것을 의미합니다.

두 번째 이미지는 부정 시작으로 **GND** 핀과 **P1** 핀이 연결된 경우에 출력할 이미지 입니다. 스크린의 랜덤 위치에 LED 불빛이 출력되기 전에, **P1** 핀이 연결된 경우 부정 시작 이미지를 출력합니다. **P1** 핀이 연결되었을 때의 동작들까지 포함시켜 코드를 수정해보세요.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P1, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            # . # . .
            . # . . .
            # . # . .
            . . . . .
            `)
    }
})
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
    if (!(false_start)) {
        start = input.runningTime()
        running = true
        led.stopAnimation()
        basic.clearScreen()
        led.plot(Math.random(5), Math.random(5))
    }
})
running = false
false_start = false
end = 0
start = 0
```

## 확장

정상적으로 반응 시간 측정이 끝나면. 다른 친구(**P2<0> 핀 사용)와 함께 반응 시간 측정 게임을 할 수도 있습니다. 누가 더 빨리 반응하는가로 게임을 진행하는 것입니다.</p> 

다음과 같은 코드를 사용하면 됩니다.:

```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
    if (!(false_start)) {
        start = input.runningTime()
        running = true
        led.stopAnimation()
        basic.clearScreen()
        led.plot(Math.random(5), Math.random(5))
    }
})
input.onPinPressed(TouchPin.P1, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            # . # . .
            . # . . .
            # . # . .
            . . . . .
            `)
    }
})
input.onPinPressed(TouchPin.P2, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            . . . # #
            . . . # #
            . . . # #
            . . . # #
            . . . # #
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            . . # . #
            . . . # .
            . . # . #
            . . . . .
            `)
    }
})
```