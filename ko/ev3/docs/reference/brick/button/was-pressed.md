# was Pressed

Check if a button was pressed earlier.

```sig
brick.buttonEnter.wasPressed()
```

The fact that a button was pressed earlier is remembered. Once **was pressed** is used, this fact is forgotten and the result is `false` the next time you check with **was pressed** button *state* is reset). But, if you press the button again before you check with **was pressed**, it will tell you `true`.

## ~hint

**Touch sensors**

Your @boardname@ has touch sensors that work like buttons. Instead of saying `enter` or `left` as the source button, use a touch sensor block with a sensor name like `touch 1`.

```typescript
if (sensors.touch1.wasPressed()) {
    console.log("Hey, I was pressed.");
}
```

Read about [touch sensors](/reference/sensors/touch-sensor) and using them as touch buttons.

## ~

## 리턴값

* a [boolean](types/boolean): `true` if the button was pressed before, `false` if the button was not pressed before

## 예시

Set the brick light to green if the `right` button was pressed before the `left` button. If not, the brick light is turned off when the `left` button is pressed.

```typescript
brick.buttonLeft.onEvent(ButtonEvent.Bumped, function() {
    if (brick.buttonRight.wasPressed()) {
        brick.setStatusLight(StatusLight.Green)
    } else {
        brick.setStatusLight(StatusLight.Off)
    }
})
```

## 참고 항목

[is pressed](/reference/brick/button/is-pressed), [on event](/reference/brick/button/on-event), [Touch sensors](/reference/sensors/touch-sensor)