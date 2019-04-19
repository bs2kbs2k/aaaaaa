# About

Welcome to the **Microsoft MakeCode** for **@boardname@**!

## @boardname@

Here's the amazing new **Love to Code** system with the @boardname@ from **[chibitronics.com](https://chibitronics.com/lovetocode/)**!

![Chibi:bit picture](https://chibitronics.com/wp-content/uploads/2017/05/09_doneprogramming.png)

## 프로그래밍 환경 : [블록](/blocks), [자바스크립트](/javascript)

You can program the @boardname@ using [Blocks](/blocks) or [JavaScript](/javascript) in your web browser:

```block
loops.forever(function () {
    lights.set(DigitalPin.D0, 1)
    loops.pause(300)
    lights.set(DigitalPin.D0, 0)
    loops.pause(300)
})
```

```typescript
loops.forever(function () {
    lights.set(DigitalPin.D0, 1)
    loops.pause(300)
    lights.set(DigitalPin.D0, 0)
    loops.pause(300)
})
```

The editor works in [most modern browsers](/browsers) and needs no installation. It even works [offline](/offline) once it's loaded.

## Compile and flash: Your program!

Compilation to machine code from [Blocks](/blocks) or [JavaScript](/javascript) happens in the browser.

When you have your code ready, you connect your @boardname@ to a computer using a [USB-to-audio cable](https://chibitronics.com/programming-chibi-chip/). Check to see if the **PROG light** on your board is red.  If it isn’t, press the **PROG button** until the light stays red. Press the [**Upload**](/upload) at the bottom of the page to move your code onto the @boardname@.

## 시뮬레이터: 코드를 테스트 해 보세요.

**@boardname@** 시뮬레이터를 이용해 작성한 프로그램코드를 실행시켜 볼 수 잇습니다. 시뮬레이터는 웹브라우저에서도 잘 동작합니다. 시뮬레이터 이용해 LED, 버튼, 디지털 입출력 핀들에 대해서도 모두 테스트 해 볼 수 있습니다.

```sim
loops.forever(function () {
    lights.set(DigitalPin.D0, 1)
    lights.set(DigitalPin.D1, 0)
    lights.set(DigitalPin.D2, 1)
    lights.set(DigitalPin.D3, 0)
    lights.set(DigitalPin.D4, 1)
    lights.set(DigitalPin.D5, 0)
    loops.pause(700)
    lights.set(DigitalPin.D0, 0)
    lights.set(DigitalPin.D1, 1)
    lights.set(DigitalPin.D2, 0)
    lights.set(DigitalPin.D3, 1)
    lights.set(DigitalPin.D4, 0)
    lights.set(DigitalPin.D5, 1)
    loops.pause(700)
})
```