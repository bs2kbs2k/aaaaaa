# on Button

Run some code when a button is pressed. A button press happens when you click, double-click, or hold down a button.

```sig
input.onButton(Button.A, ButtonEvent.Click, () => {

})
```

## 매개 변수

* **button**: the button you want to use, you choose `A`, `B` or `A+B`.
* **event**: the button press event want to run code for: > `click`: a single button is clicked  
    `double click`: the button is double-clicked  
    `hold`: click on the button and hold it for a while

## 예시

Display an icon when either button `A` or button `B` is clicked.

```blocks
input.onButton(Button.A, ButtonEvent.Click, () => {
    display.showIcon(IconType.Yes)
})
input.onButton(Button.B, ButtonEvent.Click, () => {
    display.showIcon(IconType.No)
})
```

## 참고 항목

[`||was twin button triggered||`](/reference/input/was-twin-button-triggered)