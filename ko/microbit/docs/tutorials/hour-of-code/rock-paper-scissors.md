# 가위 바위 보

## 단계 1

@boardname@ 를 흔들어 가위 바위 보 게임을 해보세요. @boardname@ 를 흔들어 `||input:on shake||` 가 실행되도록 만들어보세요.

```blocks
input.onGesture(Gesture.Shake, () => {

})
```

## 단계 2

`tool` 변수에 `||math:pick random||` 에 의해 만들어진 임의의 랜덤 수를 저장시켜보세요.

@boardname@ 를 흔들면, `0` 부터 `2` 까지 범위에서 임의의 랜덤 수가 뽑히고, 그 값이 `tool` 변수에 저장할 것입니다. (변수 이름 `tool` 은 가위 바위 보 게임에서 상대방과 승부를 내는 도구의 의미로 사용했습니다!)

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    tool = Math.random(3)
})
```

다음 단계에서, 가능한 수들 (`0`, `1`, `2`) 은 해당되는 그림으로 연결됩니다. 해당 수가 선택되면, 해당 그림이 LED 화면으로 나타납니다.

## 단계 3

`만약(if)` 을 `||math:pick random||` 아래에 붙이고, `tool` 변수에 저장된 값이 `0` 과 같은지 비교합니다.

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    let tool = Math.random(3)
    if (tool == 0) {
    }
})
```

## 단계 4

`만약(if)` 의 안쪽에 `||basic:show leds||` 블록을 넣어, 보 모양을 출력하도록 해보세요.

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    let tool = Math.random(3)
    if (tool == 0) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    }
})
```

## 단계 5

`아니면서 만약(else if)` 을 `만약(if)` 블록에 추가한 후, `tool` 변수에 저장된 값이 `1` 과 같은지 비교합니다.

`만약(if)` 블록의 왼쪽 위에 있는 톱니바퀴 모양을 누릅니다.; `아니면서 만약(else if)` 블록을 끌어다 넣어 `만약(if)` 블록을 변경할 수 있습니다.

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    let tool = Math.random(3)
    if (tool == 0) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (tool == 1) {
    }
})
```

## 단계 6

`||basic:show leds||` 을 아니면서 만약(else if) 블록 아래에 붙여, **바위**이미지를 스크린에 출력해보세요.

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    let tool = Math.random(3)
    if (tool == 0) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (tool == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
})
```

## 단계 7

`||basic:show leds||` 을 가위 이미지로 만들어, `아니면(else)` 부분에 추가합니다.

`tool` 변수에 저장되어있는 값이 `2` 와 같은지 확인할 필요는 없습니다. 왜냐하면, `2` 는 `0`, `1`, `2` 중에 확인하지 않고 남은 유일한 값이기 때문입니다. 그렇기 때문에 `아니면(else)` 을 `아니면서 만약(else if)` 대신에 사용할 수 있는 것입니다.

```blocks
let tool = 0;
input.onGesture(Gesture.Shake, () => {
    let tool = Math.random(3)
    if (tool == 0) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (tool == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    } else {
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})

```

## Step 8

자 이제 가위 바위 보 게임이 준비되었습니다! 친구들과 함께 가위 바위 보 게임을 해보세요!