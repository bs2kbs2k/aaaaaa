# 물질의 상태 변화 코드 만들기

## @description 물질의 상태 변화 장치를 위한 코드

물질의 상태를 다른 형태로 표현해보려고 해 본 적이 있나요? 공기의 온도를 기준으로 이용해서, 여러 가지 물질 상태를 시각적으로 다른 형태로 표현해봅시다.

## 단계 1: 변수 만들기.

물질의 상태 변화 실험을 위해서는 공기의 온도를 측정하기 위한 방법을 만들고 따라가야 합니다. 온도 데이터를 기록하기 위한 변수들을 만들어야 합니다. 만든 변수들에 값을 저장(설정)할 것입니다. 두(2) 개의 변수를 다음과 같이 만들어야 합니다.: “atmos_temperature”, “temperature”. 처음에 각 변수에 100 을 저장시켜둡니다. 코드를 수정해 다음과 같이 만들어보세요.

```blocks
let temperature = 100
let atmos_temperature = 100
```

## 단계 2: 고체 상태 감지하기

고체 상태를 감지하고 싶습니다. 2 번 핀이 연결되면, 공기 온도를 0 으로 출력하고 "SOLID" 라는 메시지가 스크롤이 되도록 합니다. atmos_temperature 변수의 값을 0 으로 만들고, 고체("SOLID")라는 메시지를 출력해야 합니다". 코드를 수정해 다음과 같이 만들어보세요:

```blocks
let temperature = 0
let atmos_temperature = 0
input.onPinPressed(TouchPin.P2, () => {
    atmos_temperature = 0
    basic.showString("SOLID")
})
atmos_temperature = 100
temperature = 100
```

## 단계 3: 액체 상태 감지하기

액체 상태가 되는 경우를 감지하고 싶습니다. 1 번 핀이 연결되면, 공기 온도를 80 으로 출력하고 "LIQUID" 라는 메시지가 스크롤이 되도록 합니다. atmos_temperature 변수의 값을 80 으로 만들고, 고체("SOLID")라는 메시지를 출력해야 합니다". 코드를 수정해 다음과 같이 만들어보세요:

```blocks
let temperature = 0
let atmos_temperature = 0
input.onPinPressed(TouchPin.P2, () => {
    atmos_temperature = 0
    basic.showString("SOLID")
})
input.onPinPressed(TouchPin.P1, () => {
    atmos_temperature = 80
    basic.showString("LIQUID")
})
atmos_temperature = 100
temperature = 100
```

## 단계 4: 기체 상태 감지하기

기체 상태가 되는 경우를 감지하고 싶습니다. 0 번 핀이 연결되면, 공기 온도를 80 으로 출력하고 "GAS" 라는 메시지가 스크롤이 되도록 합니다. atmos_temperature 변수의 값을 250 으로 만들고, 기체("GAS")라는 메시지를 출력해야 합니다". 코드를 수정해 다음과 같이 만들어보세요:

```blocks
let atmos_temperature = 0
let temperature = 0
input.onPinPressed(TouchPin.P0, () => {
    atmos_temperature = 250
    basic.showString("GAS")
})
input.onPinPressed(TouchPin.P2, () => {
    atmos_temperature = 0
    basic.showString("SOLID")
})
input.onPinPressed(TouchPin.P1, () => {
    atmos_temperature = 80
    basic.showString("LIQUID")
})
atmos_temperature = 100
temperature = 100
```

- *|download|* 를 눌러 프로그램 코드가 생각한데로 동작하는지 확인해보세요.

## 단계 5: 온도 올리기.

흔들면 온도가 변화되었다는 것을 출력해야 합니다. 물질의 상태 변화 실험장치를 흔들면, 온도가 증가되는 것을 나타내는 아이콘을 출력해야합니다. 흔들기 이벤트에 코드를 붙여 수정해보세요.:

```blocks
let atmos_temperature = 0
let temperature = 0
input.onGesture(Gesture.Shake, () => {
    temperature += 50
    basic.showIcon(IconNames.Triangle)
})
input.onPinPressed(TouchPin.P0, () => {
    atmos_temperature = 250
    basic.showString("GAS")
})
input.onPinPressed(TouchPin.P2, () => {
    atmos_temperature = 0
    basic.showString("SOLID")
})
input.onPinPressed(TouchPin.P1, () => {
    atmos_temperature = 80
    basic.showString("LIQUID")
})
atmos_temperature = 100
temperature = 100
```

- |download| 를 눌러 프로그램 코드가 생각한데로 동작하는지 확인해보세요.

## 단계 6: 온도 변화 출력하기.

조건식의 참(true), 거짓(false) 값에 따라 선택적으로 코드를 실행해야합니다. 온도가 변화되었다는 것을 나타내기 위해서, 아이콘들을 출력해야합니다. 2 개의 조건/선택 실행 구조를 만들것입니다. 아이콘을 출력한 다음에는, LED 스크린 지우기 블록을 이용해 화면을 지워야 합니다. 그 다음에는 100 밀리초 만큼 프로그램 실행을 일시 중지시킵니다. 이 일시 중지 함수는 프로그램의 실행 속도를 느리게 만드는데 사용할 수 있습니다.

첫 번째 조건/선택 실행 구조는 다음과 같은 논리를 사용할 것입니다.: - 물질의 온도가 공기 온도보다 낮으면, 물질의 온도를 20 만큼 증가시킵니다. - 물질의 온도가 공기 온도 이상이면, 물질의 온도를 20 만큼 감소시킵니다.

두 번째 조건/선택 실행 구조는 다음과 같은 논리를 사용할 것입니다.: - 물질의 온도가 32 도 보다 낮으면, 고체(solid)를 의미하는 기호 아이콘을 출력합니다. - 물질의 온도가 212 도 보다 낮으면, 액체(liquid)를 의미하는 기호(우산) 아이콘을 출력합니다. - 물질의 온도가 212 도 이상이면, 기체(gas)를 의미하는 기호 아이콘을 출력합니다.

```blocks
let atmos_temperature = 0
let temperature = 0
input.onGesture(Gesture.Shake, () => {
    temperature += 50
    basic.showIcon(IconNames.Triangle)
})
basic.forever(() => {
    if (temperature < atmos_temperature) {
        temperature += 20
    } else {
        temperature += -20
    }
    if (temperature < 32) {
        basic.showIcon(IconNames.Square)
    } else if (temperature < 212) {
        basic.showIcon(IconNames.Umbrella)
    } else {
        basic.showIcon(IconNames.Chessboard)
    }
    basic.clearScreen()
    basic.pause(100)
})
input.onPinPressed(TouchPin.P0, () => {
    atmos_temperature = 250
    basic.showString("GAS")
})
input.onPinPressed(TouchPin.P2, () => {
    atmos_temperature = 0
    basic.showString("SOLID")
})
input.onPinPressed(TouchPin.P1, () => {
    atmos_temperature = 80
    basic.showString("LIQUID")
})
atmos_temperature = 100
temperature = 100
```