# @boardname@ 가 있습니다!

## 단계 1

환영합니다. @boardname@ 프로그램 코드를 함께 만들어봅시다! `||basic:show string||` 블록을 `||basic:on start||` 안 쪽에 넣습니다. `"Hello"` 텍스트를 여러분의 이름으로 바꾸어 넣으세요. 입력한 텍스트가 스크롤되는 모습이 시뮬레이터로 보이나요?

```blocks
basic.showString("My Name")
```

## 단계 2

자, 출력된 텍스트가 멈춘 것을 볼 수 있습니다. `||basic:show string||` 블록을 `||input:on button pressed||` 블록 안에 붙여 넣어, **A** 버튼을 눌렀을 때 스크롤 되도록 해보세요.

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("My Name")
});
```

## 단계 3

좋습니다. 이제 버튼을 이용해 @boardname@ 가 말하도록 만들어봅시다. `||basic:show string||` 에 들어있는 텍스트를 "How are you?" 로 바꿔보세요. 다른 `||basic:show string||` 블록을 추가하고, "....." 문자열을 출력해서 @boardname@ 가 생각하는 것처럼 만들어보세요.

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("How are you?")
    basic.showString(".....");
})
```

## 단계 4

이제, @boardname@ 가 웃는 모습으로 대답할 수 있도록 만들어보세요! `||basic:show leds||` 블록을 찾아 LED 들을 클릭해 웃는 얼굴 모양을 만들어보세요. 시뮬레이터에서 **A** 버튼을 눌러, 여러분의 질문에 @boardname@ 가 응답하는지 살펴보세요.

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("How are you?")
    basic.showString(".....");
    basic.showLeds(`
    # # . # #
    # # . # #
    . . . . .
    # . . . #
    . # # # .
    `)
})
```

## 단계 5

자 이제, @boardname@ 의 기분이 어떤지 물어봅시다. 하지만, 다른 방법을 사용해보겠습니다. 물어보기 위해서 흔들기 동작을 사용할 수 있습니다. `||input:on shake||` 블록을 가져옵니다. 이전에 사용한 `||basic:show leds||` 블록을 가져다가 `||input:on shake||` 블록 안 쪽에 넣어보세요.

```block
input.onGesture(Gesture.Shake, () => {
    basic.showLeds(`
    # # . # #
    # # . # #
    . . . . .
    # . . . #
    . # # # .
    `)
})
```

## 단계 6

시간에 따라 @boardname@ 의 기분을 다르게 만들게 하고 싶습니다. 2가지 기분, 행복함과 슬픔을 사용할 것입니다. **논리** 카테고리를 눌러 `||logic:if then else||` 블록을 가져옵니다. 그 블록을 `||input:on shake||` 안에 넣은 후, `||basic:show leds||` 블록을 `||logic:if then||` 안쪽에 넣습니다.

```block
input.onGesture(Gesture.Shake, () => {
    if (true) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . . . .
            # . . . #
            . # # # .
            `)
    } else {

    }
})
```

## 단계 7

`||basic:show leds||` 을 복사합니다. (오른쪽 클릭 후, 복사를 누릅니다.) 새로 만들어진 블록을 `||logic:else||` 부분에 넣습니다. `||logic:if then else||` 의 한 부분입니다. 이제, 그 중 하나를 찡그린 얼굴로 바꿉니다.

```block
input.onGesture(Gesture.Shake, () => {
    if (true) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . . . .
            # . . . #
            . # # # .
            `)
    } else {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . . . .
            . # # # .
            # . . . #
            `)
    }
})
```

## Step 8

`||logic:if||` 의 조건을 바꿔 기분이 변하는지 살펴봅니다. `참(true)` 을 `거짓(false)` 으로 바꾸고, 시뮬레이터에서 **SHAKE** 점을 찾아 눌러봅니다.

## Step 9

@boardname@ 가 단순하게 반응하지 않도록 하기 위해, 랜덤으로 기분을 만들어봅시다. `||math:pick random true or false||` 블록을 **계산** 카테고리에서 찾습니다. 그 블록을 가져와서, `||logic:if||` 블록의 조건 부분에 있는 `참(true)` 조건을 바꾸어 넣습니다.

```block
input.onGesture(Gesture.Shake, () => {
    if (Math.randomBoolean()) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . . . .
            # . . . #
            . # # # .
            `)
    } else {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . . . .
            . # # # .
            # . . . #
            `)
    }
})
```

## 단계 10

이제, 시뮬레이터에 있는 **SHAKE** 점을 몇 번 눌러, @boardname@ 의 기분이 어떻게 나타나는지 살펴보세요. 흠, 기분이 달라집니다!

## 단계 11

너무 멋지게 잘 해냈습니다! Microsoft 메이크코드 활동을 성공적으로 완료했습니다. @boardname@ 를 가지고 있다면, `|Download|` 버튼을 눌러 여러분이 만든 코드를 업로드시켜보세요.