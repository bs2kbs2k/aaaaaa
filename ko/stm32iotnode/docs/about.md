# About

The **STM32 IoT Node Microsoft MakeCode editor** allows to program the @boardname@.

## 프로그래밍 환경 : [블록](/blocks), [자바스크립트](/javascript)

You can program the @boardname@ using [Blocks](/blocks) or [JavaScript](/javascript) in your web browser.

```blocks
forever(function() {
    pins.LED.digitalWrite(true)
    pause(500)
    pins.LED.digitalWrite(false)
    pause(500)    
})
```

```typescript
forever(function() {
    pins.LED.digitalWrite(true)
    pause(500)
    pins.LED.digitalWrite(false)
    pause(500)    
})
```

The editor work in [most modern browsers](/browsers), work [offline](/offline) once loaded and do not require any installation.

## [컴파일, 프로그램 업로드: 만든 프로그램을 마이크로비트에 업로드!](/device/usb)

When you have your code ready, you connect your @boardname@ to a computer via a USB cable **then press the reset button** so it appears as a mounted drive (named @boardname@).

Compilation to machine code from [Blocks](/blocks) or [JavaScript](/javascript) happens in the browser. You save the binary program to a **.bin** file, which you then copy to the @boardname@ drive, which flashes the device with the new program.

## 시뮬레이터: 코드를 테스트 해 보세요.

You can run your code using the Metro Express simulator, all within the confines of a web browser.

```sim
forever(function() {
    pins.LED.digitalWrite(true)
    pause(500)
    pins.LED.digitalWrite(false)
    pause(500)
})
```

## 오픈소스

Maker is open source on GitHub at https://github.com/Microsoft/pxt-stm32-iot-node .