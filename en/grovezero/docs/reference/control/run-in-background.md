# run In Background

Run some other code at the same time that your main program code runs.

```sig
control.runInBackground(function() {})
```

Sometimes you want your program to work on more than one thing at a time. The main part of your program is always put in [`||on start||`](/blocks/on-start). But, you can also put some other part of your program in `||run in background||`. This is a block that runs code seperately from the code in `||on start||`. This is useful when you want your program to keep doing important things and you don't want to wait for some other actions to happen first.

As an example, you could have a small task to continuously scroll a greeting on the LED Matrix. This is placed inside a `||run in background||` block:

```blocks
let greeting = "Good morning!"
let scrollit = true

control.runInBackground(function() {
    while (scrollit) {
        display.showString(greeting)
        loops.pause(200)
    }
})
```

Code is added to the main part of the program to turn the greeting on. It sets the greeting, waits for `5` seconds and changes the greeting. Then, it waits for `5` more seconds and stops greeting scroller.

```blocks
let scrollit = true
let greeting = "Good morning!"
loops.pause(5000)
greeting = "Have a donut"
loops.pause(5000)
scrollit = false
display.showString("")
```

## Parameters

* **a**: the code to run in the background.

## Example

### Happy status

Display a smiley face in a happy task which also checks for happy status. Button **A** is the sad button. If it's pressed, happy status becomes `false` and the LED Matrix shows a sad face. The happy task ends and things stay sad.

```blocks
let beHappy = true
input.onButton(Button.A, ButtonEvent.Click, function () {
    beHappy = false
})
control.runInBackground(function () {
    display.showIcon(IconType.Smile, OrientationType.Rotate0)
    while (beHappy) {
        loops.pause(250)
    }
    display.showIcon(IconType.Sad, OrientationType.Rotate0)
})
```