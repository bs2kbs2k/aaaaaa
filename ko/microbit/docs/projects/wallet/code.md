# 테이프 지갑 코드 만들기

## 간단한 애니메이션

[무한 반복 실행](/reference/basic/forever) 과 [LED 출력](/reference/basic/show-leds) 을 복합적으로 사용해 애니메이션을 만들어봅시다.:

```blocks
basic.forever(() => {
    basic.showLeds(`
        # # . # #
        # # . # #
        . # # # .
        . # . # .
        . # . # .
        `)
    basic.showLeds(`
        . . # . .
        . . # . .
        # . . . #
        # . # . #
        # . # . #
        `)
})
```

@boardname@ 에 프로그램 코드를 업로드 한 후, 확인해보세요.

## 주머니에 넣으면 애니메이션이 멈추도록 만들기

지갑을 주머니에 넣으면, 배터리를 아끼기 위해서 LED 화면을 모두 꺼야합니다.

지갑이 주머니에 들어갔다는 것을 어떻게 알 수 있을까요? 주머니 안은 깜깜하게 어둡습니다... [LED 스크린 빛 센서 밝기](/reference/input/light-level) 를 이용하면 주머니 안에 들어갔다는 것을 알아낼 수 있습니다!

한 개의 [만약(if)](/blocks/logic/if) 조건문을 사용해, LED 스크린에 불을 켜야 할 지를 빛의 밝기를 감지해 검사할 수 있습니다. 빛이 어둡다면, 배터리 전기를 아끼기 위해 몇 초 동안 화면을 끄면 됩니다.

```blocks
basic.forever(() => {
    if (input.lightLevel() > 16) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . # # # .
            . # . # .
            . # . # .
            `)
        basic.showLeds(`
            . . # . .
            . . # . .
            # . . . #
            # . # . #
            # . # . #
            `)
    } else {        
        // clear screen and wait
        basic.clearScreen()
        basic.pause(3000)
    }
})
```