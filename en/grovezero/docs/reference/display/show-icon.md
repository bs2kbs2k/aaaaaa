# show Icon

Display an icon (pixel image) on the LED Matrix.

```sig
display.showIcon(IconType.Smile)
```

There are built-in icons you can display. You select the one you want from the list in the block or from the suggestions in the JavaScript editor when you type `IconType`.

## Parameters

* **icon**: the icon you want to show, like: `heart`, `small heart`, `yes` , `no`, or `grove zero`.
* **orientation**: the direction you want the icon rotated when it is shown. Use this if you want the icon turned from its normal direction. >`0°`: no rotation  
    `90°`: rotate 90 degrees clockwise  
    `180°`: rotate 180 degrees clocwise (upside down)  
    `270°`: rotate 270 degrees clockwise (upside down and then another 90 degrees)

## Example

Show a happy face on the LED matrix when there is light. Show a sad face when it's dark.

```blocks
sensor.onLight(LightEvent.Light, function () {
    display.showIcon(IconType.Smile)
})
sensor.onLight(LightEvent.Dark, function () {
    display.showIcon(IconType.Sad)
})
```

## See also

[`||show number||`](/reference/display/show-number) [`||show string||`](/reference/display/show-string)