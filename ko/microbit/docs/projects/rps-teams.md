# 팀 가위 바위 보

## ~avatar avatar

대규모 멀티플레이어 가위 바위 보 게임입니다!

## ~

https://youtu.be/8ztOmdZi5Pw

가위 바위 보 게임은, 원래 두 명이 함께하는 게임입니다... 하지만, 더 많은 사람들이 함께 할 수도 있습니다! 두 명 이상의 사람들이 함께 가위 바위 보 게임을 하게 되면, 팀 게임이 됩니다: 모든 플레이어들이 동시에 흔들면, **바위(rock)**, **보(paper)**, **가위(scissors)** 를 나타내는 번호와 아이콘이 모든 플레이어의 화면에 나타나게 됩니다. 가장 많은 개수가 나온 플레이어가 이기게 됩니다.

[기본 버전의 RPS(가위바위보) 게임](/projects/rock-paper-scissors) 의 기본 코드를 수정해서, @boardname@ 가 같은 팀의 인원 수를 세고 표시할 수 있도록 할 것입니다. @boardname@ 의 **라디오** 통신을 이용해서, 보드의 상태를 다른 보드들과 송수신 할 수 있습니다.

자 함께 시작해보세요!

## 시작 블록

원래의 게임 코드에서 시작해봅시다. 원래의 코드에서는 `||input:on shake||` 를 통해 가위 바위 보를 선택하고, 선택된 아이콘을 출력합니다. 아래 코드를 살펴보면서, 다시 기억해내 보세요.

```blocks
let tool = 0
input.onGesture(Gesture.Shake, () => {
    tool = Math.random(3)
    if (tool == 0) {
        basic.showIcon(IconNames.SmallSquare)
    } else if (tool == 1) {
        basic.showIcon(IconNames.Square)
    } else {
        basic.showIcon(IconNames.Scissors)
    }
});
```

## 단계 1: 리팩토링

**리팩토링(Refactoring)** 은 코딩에서 사용되는 재미있는 단어입니다. 리팩토링은 `재조직(reorganizing)` 보다 더 많은 것을 의미합니다. 여기에서는 바위(rock)/보(paper)/가위(scissor) 아이콘을 출력하는 코드를, `||basic:forever||` 반복 구조 안으로 이동시킬 것입니다.

```blocks
let tool = 0
input.onGesture(Gesture.Shake, () => {
    tool = Math.random(3)
})

basic.forever(() => {
    if (tool == 0) {
        basic.showIcon(IconNames.SmallSquare)
    } else if (tool == 1) {
        basic.showIcon(IconNames.Square)
    } else {
        basic.showIcon(IconNames.Scissors)
    }
});
```

## 단계 2: 라디오를 통해 상태 전송하기

`tool` 변수의 값을 라디오 기능을 이용해, 다른 @boardname@ 의 `||basic:forever||` 구조로 전달합니다. 라디오 데이터 패킷이 제대로 전달되지 않을 수 있기 때문에, 계속해서 전송시키는 것이 좋습니다

또한 라디오 그룹을 설정하고, 나중을 위해 그 장치의 시리얼 번호도 함께 전송합니다.(시리얼 번호는 @boardname@ 의 고유한 번호입니다.)

```blocks
let tool = 0
input.onGesture(Gesture.Shake, () => {
    tool = Math.random(3)
})

basic.forever(() => {
    radio.sendNumber(tool)
    if (tool == 0) {
        basic.showIcon(IconNames.SmallSquare)
    } else if (tool == 1) {
        basic.showIcon(IconNames.Square)
    } else {
        basic.showIcon(IconNames.Scissors)
    }
});
radio.setGroup(10)
radio.setTransmitSerialNumber(true)
```

## 단계 3: 팀 명단

이렇게 하면, 모든 플레이어들이 자기가 뽑은 수를 다른 플레이어들에게 계속해서 송신하게 됩니다. 이제, 다른 플레이어들이 송신하는 상태들을 수신하고 카운트 할 수 있도록 해봅시다.

**[배열](/types/array)** 을 만들어, 현재 같은 팀에 속한 모든 플레이어들을 기록해둡니다. `players` 배열은, 마치 팀 명단과 같습니다.: 같은 가위 바위 보를 선택한 모든 @boardname@ 들의 시리얼 번호를 가지고 있습니다.

```block
let players: number[] = [0]
```

## 단계 4: 메시지 수신하기(파트 1)

`||radio:on radio received||` 이벤트 안에서 다른 @boardname@ 의 상태를 수신합니다. **톱니바퀴** 모양을 클릭해 `serial` 매개 변수를 추가합니다. 이는 패킷을 보낸 장치를 알아내는데 필요합니다.

수신된 데이터를 통해 3 가지 값을 계산합니다.:

* `match`, 어떤 @boardname@ 보드가 보낸 값이, 지금 선택한 가위 바위 보와 같은지 여부를 나타내는 불(참/거짓) 값.
* `player_index`, 다른 보드의 시리얼 번호가 저장되어있는 배열의 위치. 배열에 해당 시리얼 번호가 저장되어있지 않으면 `-1` 일 것입니다.
* `found`, @boardname@ 의 시리얼 번호가 `players` 배열 안에 들어있는지 여부를 나타내는 불(참/거짓) 값.

```blocks
let match = false
let player_index = 0
let players: number[] = [0]
let tool = 0
let found = false
radio.onDataPacketReceived(({ receivedNumber, serial: serialNumber }) => {
    match = tool == receivedNumber
    player_index = players.indexOf(serialNumber)
    found = player_index >= 0
})
```

## 단계 5: 메시지 수신하기(파트 2)

`match` 값과 `found` 값의 조합에 따라, 다르게 처리해야 합니다:

* **만약(if)** 다른 장치에서 보낸 가위 바위 보가 같아서 `match` 가 참(true) **이면서(and)**, 그 장치를 배열에서 `찾을 수 없음(not found)` **이면(then)**, 그 장치의 시리얼 번호를 **추가(add)** 하기 위해 `players` 배열에 저장해야 합니다.
* **만약(if)** 다른 장치에서 보낸 가위 바위 보가 달라서 `match` 가 거짓(false) **이면서(and)**, 그 장치를 배열에서 `찾을 수 있음(not found)` **이면(then)**, 그 장치의 시리얼 번호를 **제거(remove)** 하기 위해 `players` 배열에서 삭제해야 합니다.

위 규칙을 2개의 `||logic:if then||` 조건문을 이용해 그 시리얼 번호를 추가해야 할 지, 삭제해야 할 지를 결정합니다.

```blocks
let match = false
let player_index = 0
let players: number[] = [0]
let tool = 0
let found = false
let temp = 0
radio.onDataPacketReceived(({ receivedNumber, serial: serialNumber }) => {
    match = tool == receivedNumber
    player_index = players.indexOf(serialNumber)
    found = player_index >= 0
    if (match && !(found)) {
        players.push(serialNumber)
    } 
    if (!(match) && found) {
        temp = players.removeAt(player_index)
    }
})
```

## 단계 6: 팀 재설정하기

일부 플레이어가 팀을 떠나면 어떻게 되나요? 그 플레이어 보드의 상태 전송이 중단되어도, 플레이어 리스트에 계속 남아있을 것입니다. 이러한 문제를 방지하기 위해, 장치를 흔들 때마다 `players` 배열을 초기화하도록 합니다.:

```block
input.onGesture(Gesture.Shake, () => {
    let players: number[] = [0]
    let tool = Math.random(3)
})
```

## 단계 7: 팀 점수 보이기

팀 점수는 그 팀에 속한 플레이어의 수입니다... 플레이어의 수는, `길이(length)` 를 알아내면 됩니다. `players` 배열의 길이(크기)가 플레이어의 인원수입니다. `||basic:show number||` 블록을 `||basic:forever||` 반복 구조 안에 넣어, 반복해서 계속 출력하도록 합니다.

```block
let players: number[] = [0]
let tool = 0
basic.forever(() => {
    basic.showNumber(players.length)
})
```

## 최종 코드

이제 모든 작은 프로그램들을 하나로 붙여 만들어야 합니다. 모든 단계들을 주의 깊게 살펴보면서, 여러 가지 기능들을 함께 결합하세요. 모두 결합하고 나면, 다음과 같은 프로그램으로 완성될 것입니다. 프로그램을 업로드해서, **많은~ 친구들**과 함께 해보세요!

```blocks
let temp = 0
let found = false
let player_index = 0
let tool = 0
let match = false
let players: number[] = []
input.onGesture(Gesture.Shake, () => {
    players = [0]
    tool = Math.random(3)
})
radio.onDataPacketReceived( ({ receivedNumber, serial: serialNumber }) =>  {
    match = tool == receivedNumber
    player_index = players.indexOf(serialNumber)
    found = player_index >= 0
    if (match && !(found)) {
        players.push(serialNumber)
    }
    if (!(match) && found) {
        temp = players.removeAt(player_index)
    }
})
basic.forever(() => {
    radio.sendNumber(tool)
    if (tool == 0) {
        basic.showIcon(IconNames.SmallSquare)
    } else if (tool == 1) {
        basic.showIcon(IconNames.Square)
    } else {
        basic.showIcon(IconNames.Scissors)
    }
    basic.showNumber(players.length)
})
players = [0]
radio.setGroup(10)
radio.setTransmitSerialNumber(true)
```

```package
radio
```