# 반딧불이

## ~ avatar

여러분의 @boardname@ 들을 반딧불이들로 만들어보세요.

## ~

https://youtu.be/ZGvtnE1Wy6U

## 어떻게 반딧불이들이 서로 같이 반짝일 수 있을까요?

http://ncase.me/fireflies/ 에 접속해 반딧불이들의 동기화 현상에 대해서 살펴보세요.

## 반딧불이 코드 만들기

여러 개의 @boardname@ 들을 여러 마리의 반딧불이 처럼 반짝이도록 만드려고 합니다.(@boardname@ 를 각각 한 마리의 반딧불이 처럼) 핵심 포인트들을 함께 살펴보도록 합시다.:

### "각각의 반딧불이들은 내부적으로 자기 시계를 가지고 있습니다..."

이 활동에서는 시계를 카운터처럼 사용하기 때문에, `clock` 변수를 먼저 프로그램에 추가합니다.

```block
// the clock ticker
let clock = 1
```

### "...각 반딧불이의 시계가 '12 를 가리키면', 반딧불을 반짝입니다."

시계 시간을 1 만큼 씩 증가시키기 위해, `||basic:forever||` 을 사용할 수 있습니다. 각 반딧불이 시계의 시간이 "정오" (`8` 을 정오로 선택)가 되면, LED 스크린을 간단히 켭니다.(게임 스코어 애니메이션을 사용합니다.)

```block
// the clock ticker
let clock = 0
basic.forever(() => {
    // if clock "hits noon", flash the screen
    if (clock >= 8) {
        // flash
        game.addScore(1)
        // wait for 2 ticks
        basic.pause(200)
        // reset the clock
        clock = 0
    } else {
        // just wait a bit
        basic.pause(100)
        // increment the clock
        clock += 1
    }
})
```

### 근처에 있는 반딧불이가 반짝이면, 그 반딧불이의 시계도 조금 더 빨리 흐르게 만듭니다

@boardname@ 는 근처에 있는 @boardname@ 에 라디오 메시지를 전송할 수 있습니다. 라디오 메시지들을 이용해 불빛들을 "반짝이도록" 할 수 있습니다.

반딧불이의 불빛을 반짝이면서 동시에, `||radio:radio send number||` 을 사용해 원하는 수를 전송하도록 만들 수 있습니다.:

```block
// the clock ticker
let clock = 0
basic.forever(() => {
    // if clock "hits noon", flash the screen
    if (clock >= 8) {
        // notify neighbors
        radio.sendNumber(0)
        // flash
        game.addScore(1)
        // wait for 2 ticks
        basic.pause(200)
        // reset the clock
        clock = 0
    } else {
        // just wait a bit
        basic.pause(100)
        // increment the clock
        clock += 1
    }
})
```

When a firefly receives a radio packet **and** it is not sending packet , it increments its clock by one:

```block
// the clock ticker
let clock = 0
radio.onDataPacketReceived(() => {
    // advance clock to catch up neighbors
    if (clock < 8) {
        clock += 1
    }
})
```

## 모두 함께 결합시키기

https://youtu.be/XzZeB4yYnEw

가능한 많은 @boardname@ 에 다음 프로그램을 업로드하고, 어두운 방에서 실험해 보세요!

**참고:** `||radio:radio set group||` 블록을 이용해 반딧불이들이 서로 통신하는 그룹을 설정했습니다.

```blocks
// the clock ticker
let clock = 0
radio.onDataPacketReceived(() => {
    // advance clock to catch up neighbors
    clock += 1
})
basic.forever(() => {
    // if clock hits noon, flash the screen
    if (clock >= 8) {
        // notify neighbors
        radio.sendNumber(0)
        // flash
        game.addScore(1)
        // wait for 2 ticks
        basic.pause(200)
        // reset the clock
        clock = 0
    } else {
        // just wait a bit
        basic.pause(100)
        // increment the clock
        clock += 1
    }
})
radio.setTransmitPower(1)
radio.setGroup(12)
```

```package
radio
```