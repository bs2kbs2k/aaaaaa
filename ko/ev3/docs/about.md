# About

Welcome to the **Microsoft MakeCode** editor for the **@boardname@**!

## 프로그래밍 환경 : [블록](/blocks), [자바스크립트](/javascript)

You can program the @boardname@ using [Blocks](/blocks) or [JavaScript](/javascript) in your web browser:

```blocks
brick.buttonEnter.onEvent(ButtonEvent.Bumped, () => {
    motors.largeA.run(50)
})
```

```typescript
brick.buttonEnter.onEvent(ButtonEvent.Bumped, () => {
    motors.largeA.run(50)
})
```

The editor works in [most modern browsers](/browsers). It works [offline](/offline) once loaded and doesn't require any installation. Take a look at some of the [features](/about/editor-features) of the editor.

## 컴파일, 프로그램 업로드: 만든 프로그램을 마이크로비트에 업로드!

When you have your code ready, you connect your EV3 Brick to a computer with a USB cable so it appears as an attached drive (named **@drivename@**).

Compilation to machine code from [Blocks](/blocks) or [JavaScript](/javascript) happens in the browser. You save the binary program to a **.uf2** file, which you then copy to the **@drivename@** drive. The process of copying will flash the device with the new program.

### ~ hint

Not seeing the **@drivename@** drive? Make sure to upgrade your firmware at https://ev3manager.education.lego.com/. Try these [troubleshooting](/troubleshoot) tips if you still have trouble getting the drive to appear.

### ~

## 시뮬레이터: 코드를 테스트 해 보세요.

You can run your code using the @boardname@ simulator, all inside the same browser window. The simulator has support for the EV3 Brick screen, buttons, sensors, and motors.

```sim
brick.buttonEnter.onEvent(ButtonEvent.Bumped, () => {
    motors.largeA.run(50)
    motors.mediumD.run(50)
    sensors.touch1.pauseUntil(ButtonEvent.Pressed)
    sensors.ultrasonic4.pauseUntil(UltrasonicSensorEvent.ObjectDetected)
})
```