# About

Welcome to the **Microsoft MakeCode** editor for the **Seeed Studio Grove Zero**!

## Programming: Blocks or JavaScript

You can program Grove Zero using [blocks](/blocks) or [JavaScript](/javascript) in your web browser.

```sig
input.onButton(Button.A, ButtonEvent.Click, function () {
    display.showIcon(IconType.Heart)
})
```

The editor works in most modern browsers, work offline once loaded and do not require any installation.

## 컴파일, 프로그램 업로드: 만든 프로그램을 마이크로비트에 업로드!

When you have your code ready, you connect your Grove Zero Main Board to a computer via a USB cable then press the reset button twice so it appears as a mounted drive（Grove Zero）.

Compilation to machine code from Blocks or JavaScript happens in the browser. You save the binary program to a .uf2 file, which you then copy to the Grove Zero drive, which flashes the device with the new program.