# RC 자동차 해킹 코드 만들기

## 단계 1: Kitronik 패키지 추가하기

Kitronik 모터 드라이브 보드를 프로그래밍 할 수 있는 패키지가 있습니다. 그 패키지를 추가해야합니다.

* **고급** 을 누릅니다.
* **패키지 추가** 를 누릅니다.
* `kitronik` 을 입력하고, **엔터** 를 누릅니다.
* **kitronik-motor-driver** 패키지를 선택합니다.

패키지가 로드되면, 왼쪽의 도구 상자에 새로운 **Kitronik** 카테고리가 나타나게 됩니다.

## 단계 2: 이리 저리 움직여보세요!

https://youtu.be/pD6tM1nXCPA

첫 번째 프로그램은, `A` 버튼을 누르고 있는 동안 5 초 동안 원을 그리며 회전하는 것입니다. 이는 간단히 5 초 동안 모터 컨트롤러에 전기를 공급하면 되는 것입니다.

```blocks-ignore
input.onButtonPressed(Button.A, () => {
    basic.showIcon(IconNames.Happy)
    kitronik.motorOn(kitronik.Motors.Motor1, kitronik.MotorDirection.Reverse, 100)
    kitronik.motorOn(kitronik.Motors.Motor2, kitronik.MotorDirection.Forward, 100)
    basic.pause(5000)
    kitronik.motorOff(kitronik.Motors.Motor1)
    kitronik.motorOff(kitronik.Motors.Motor2)
    basic.showIcon(IconNames.SmallDiamond)
})
```

### ~ hint

**전자회로 보호하기**

컴퓨터에 @boardname@ 를 연결할 때에는 반드시 엣지 컨넥터에서 분리한 상태로 연결해야 합니다. 그렇게 해야 혹시라도 발생할지 모르는 전기 전자적 문제 발생을 방지할 수 있습니다.

### ~

모터 드라이브에 전기선을 연결하는 방법에 따라, 모터가 앞으로 회전하지 않고 반대로 뒤로 회전할 수 있습니다. 그런 경우, 전선이 연결된 방향을 서로 바꾸거나, 프로그램 코드 안에서 `모터 출력 방향` 을 반대로 바꾸는 방법을 사용해 해결할 수 있습니다.

## Step 3: 8 자 돌리기

https://youtu.be/agor9wtiAkE

5 초 이동 후 정지 시키는 대신, 방향 회전을 위한 스티어링 모터의 방향을 반대로 돌립니다. 그렇게 하면 8 자 모양으로 회전하면서 움직이게 됩니다.

```blocks-ignore
input.onButtonPressed(Button.A, () => {
    basic.showIcon(IconNames.Happy)
    kitronik.motorOn(kitronik.Motors.Motor1, kitronik.MotorDirection.Reverse, 100)
    kitronik.motorOn(kitronik.Motors.Motor2, kitronik.MotorDirection.Forward, 100)
    basic.pause(3500)
    kitronik.motorOn(kitronik.Motors.Motor2, kitronik.MotorDirection.Reverse, 100)
    basic.pause(3500)
    kitronik.motorOff(kitronik.Motors.Motor1)
    kitronik.motorOff(kitronik.Motors.Motor2)
    basic.showIcon(IconNames.SmallDiamond)
})
```

잘 했습니다! 자동차를 움직일 수 있는 프로그램 코드가 준비되었습니다! 이제 다른 @boardname@ 를 준비해서 무선 리모트로 자동차를 조종할 수 있도록 해보겠습니다.

### ~button /projects/rc-car/connect

RC 자동차 해킹 무선 연결하기

### ~

```package
pxt-kitronik-motor-driver=github:kitronikltd/pxt-kitronik-motor-driver#v0.0.3
```