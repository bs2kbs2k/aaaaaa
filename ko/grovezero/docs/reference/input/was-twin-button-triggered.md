# was Twin Button triggered

See if a combination button press has happened.

```sig
input.wasTwinButtonTriggered(Button.AB, ButtonEvent.Click)
```

You can check to see if something happens with both buttons at the same time. If you choose a twin button event for `A+B`, you can see if button `A` was held when button `B` was clicked. So, you can mix events for both buttons to create many button press combinations.

Button combinations can mix clicks, double-clicks, and a button holds.

* **button**: the button you want a press event for, you choose `A`, `B` or `A+B`.
* **event**: the button press event want to run code for: > `click`: a single button is clicked  
    `double click`: the button is double-clicked  
    `held`: the button is clicked and held for a while

## 예시

Check to see if button `B` is clicked when something else is going on with button `A`. If this happens, show the smiley face icon on the LED display.

```blocks
loops.forever(function () {
    if (input.wasTwinButtonTriggered(Button.AB, ButtonEvent.Click)) {
        display.showIcon(IconType.Smile)
    }
})
display.showIcon(IconType.Sad)
```

## 참고 항목

[`||on button||`](/reference/input/on-button)