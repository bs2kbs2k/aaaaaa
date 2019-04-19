# 다음 이벤트가 발생하면 실행

Run some code when a button is clicked, pressed down, or released.

```sig
brick.buttonEnter.onEvent(ButtonEvent.Bumped, function () {

});
```

## ~hint

**Touch sensors**

Your @boardname@ has touch sensors that work like buttons. Instead of saying `enter` or `left` as the source button, use a touch sensor block with a sensor name like `touch 1`.

```block
sensors.touch1.onEvent(ButtonEvent.Pressed, function () {
    brick.setStatusLight(StatusLight.Orange);
});
```

Read about [touch sensors](/reference/sensors/touch-sensor) and using them as touch buttons.

## ~

## 매개 변수

* **ev**: the button action to run some code for. The button actions (events) are: > * `click`: button was clicked (pressed and released) > * `up`: button is released from just being pressed > * `down`: button is just pressed down
* **body**: the code you want to run when something happens with a button

## 예시

Check for event on the ENTER button. Put a message on the screen when the button is pressed, clicked, or released.

```blocks
brick.showString("ENTER is: UP", 1);
brick.buttonEnter.onEvent(ButtonEvent.Released, function () {
    brick.showString("ENTER is: UP      ", 1);
});
brick.buttonEnter.onEvent(ButtonEvent.Pressed, function () {
    brick.showString("ENTER is: DOWN    ", 1);
});
brick.buttonEnter.onEvent(ButtonEvent.Bumped, function () {
    brick.showString("ENTER was: CLICKED", 1);
});
```

### 참고 항목

[is pressed](/reference/brick/button/is-pressed), [was pressed](/reference/brick/button/was-pressed),

[Touch sensor](/reference/sensors/touch-sensor)