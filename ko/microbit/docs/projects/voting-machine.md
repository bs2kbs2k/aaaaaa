# 투표 기계

## ~ avatar

여러 대의 @boardname@ 를 이용해 투표 기계를 만들어보세요!

## ~

https://youtu.be/77HOqf8BaNg

이 프로젝트에서, **voter** 프로그램이 @boardname@ 에 업로드됩니다. 투표자들은 버튼을 이용해 `yes` 또는 `no` 를 선택하며, 그 결과는 라디오 기능을 이용해 **표시판** @boardname@ 로 전송됩니다. 표시판에서는 투표자 1명 당 1개의 LED 로 투표 결과를 보여줍니다.

## 투표(voter) 프로그램

`A` 버튼은 NO, `B` 버튼은 YES 라고 생각하고, 투표(voter) 프로그램은 다음과 같이 동작합니다.:

### NO 투표 전송

`A` 버튼이 눌리면, `0` 값이 라디오를 통해 전송되고, `X` 모양이 스크린에 나타납니다.

```block
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(0)
    basic.showIcon(IconNames.No)
})
```

### YES 투표 전송

`B` 버튼이 눌리면, `255` 값이 라디오를 통해 전송되고, `Y` 모양이 스크린에 나타납니다.

```block
input.onButtonPressed(Button.B, () => {
    radio.sendNumber(255)
    basic.showIcon(IconNames.Yes)
})
```

### 장치 시리얼 번호 전송 설정

각 투표들을 추적하기 위해, 각 장치의 고유한 시리얼번호도 함께 전송하도록 할 것입니다.

```block
radio.setTransmitSerialNumber(true)
```

### 라디오 그룹 설정

임의로 `4` 를 골라 통신을 위한 그룹 번호로 사용하도록 합니다.

```block
radio.setGroup(4)
```

모든 부분들을 함께 모아, 다음과 같은 투표 프로그램을 완성합니다.:

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(0)
    basic.showIcon(IconNames.No)
})
input.onButtonPressed(Button.B, () => {
    radio.sendNumber(255)
    basic.showIcon(IconNames.Yes)
})
radio.setGroup(4)
radio.setTransmitSerialNumber(true)
basic.showIcon(IconNames.Ghost)
```

## 표시판

[radio dashboard](/examples/radio-dashboard) 에 투표 현황판 코드가 있습니다.

다운로드한 프로그램코드를 @boardname@ 에 업로드하면, 결과를 확인할 수 있습니다.

어떤 @boardname@ 에서 전송된 메시지가 표시판에서 수신되면, 그 보드를 의미하는 픽셀을 찾습니다.(그리고 그 정보를 기억합니다.) 그리고, 그 보드에서 전달된 값을 LED 밝기로 사용합니다.

어떤 상황에서 보드가 메시지를 전송하지 못하면, 그 보드를 의미하는 픽셀이 반짝이기 시작할 것입니다. 그리고 시간이 더 지나면, 그냥 꺼지게 될 것입니다.

```package
radio
```