# About

Welcome to the **Microsoft MakeCode** editor for the **@boardname@**!

## ~ hint

Heads up! This editor only works for the Circuit Playground **Express**, not the **Classic**.

## ~

## Circuit Playground Express

Check out the awesome hardware spec at **[Adafruit.com](https://www.adafruit.com/product/3333)**.

![@boardname@ image](https://cdn-shop.adafruit.com/970x728/3333-04.jpg)

## 프로그래밍 환경 : [블록](/blocks), [자바스크립트](/javascript)

You can program the @boardname@ using [Blocks](/blocks) or [JavaScript](/javascript) in your web browser:

```block
input.buttonA.onEvent(ButtonEvent.Click, () => {
    light.showRing(`blue blue blue blue blue blue blue blue blue blue`)
})
```

```typescript
input.buttonA.onEvent(ButtonEvent.Click, () => {
    light.showRing(`blue blue blue blue blue blue blue blue blue blue`)
})
```

The editor work in [most modern browsers](/browsers), work [offline](/offline) once loaded and do not require any installation.

## [컴파일, 프로그램 업로드: 만든 프로그램을 마이크로비트에 업로드!](/device/usb)

When you have your code ready, you connect your @boardname@ to a computer via a USB cable **then press the reset button** so it appears as a mounted drive (named **CPLAYBOOT**).

Compilation to machine code from [Blocks](/blocks) or [JavaScript](/javascript) happens in the browser. You save the binary program to a **.uf2** file, which you then copy to the **CPLAYBOOT** drive, which flashes the device with the new program.

## 시뮬레이터: 코드를 테스트 해 보세요.

You can run your code using the **@boardname@** simulator, all within the confines of a web browser. 시뮬레이터에서는 LED 스크린 출력, 버튼 입력 뿐만 아니라, 자기(나침반) 센서, 가속도 센서, 디지털 입출력 I/O 핀과 같은 기능들도 테스트 해 볼 수 있습니다.

```sim
forever(() => {
    light.showAnimation(light.rainbowAnimation, 1000)
})
```

```package
light
```