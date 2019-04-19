# rgb

Combine the red, green, and blue parts of light into an RGB color.

```sig
rgb.rgb(255, 255, 255);
```

### RGB란? #rgbdesc

In your programs, light color is known by the amount of three separate colors added together: **red**, **green**, and **blue**. These colors are known as *primary* colors and all the other colors are really a combination of these colors.

Think of taking different colors of paint and mixing them together. Mix an equal amount of red paint with an equal amount of green paint. Don't use any blue paint though. What you get from both red and green is yellow. So, in your program you can make yellow like this:

```block
let yellow = rgb.rgb(255, 255, 0)
```

In the same way you can make pink but use blue this time and take away the green:

```block
let pink = rgb.rgb(255, 0, 255)
```

## 매개 변수

* **red**: a [number](/types/number) that is the amount of red light (between 0 and 255), like: 128
* **green**: a [number](/types/number) that is the amount green light (between 0 and 255), like: 51
* **blue**: a [number](/types/number) that is the amount of blue light (between 0 and 255), like: 255

## 리턴값

* a [number](/types/number) that is the RGB value for the three color numbers.

## 예시

Make a new color of yellow to use on the RGB LED. Try the new color when you press the pin `D0`.

```blocks
let myYellow = rgb.rgb(255, 228, 181)
let myBlack = rgb.rgb(0, 0, 0)
let showColor = myYellow

loops.forever(function () {
    if (sensing.pressed(DigitalPin.D0)) {
        rgb.setColor(showColor)
        if (showColor == myYellow) {
            showColor = myBlack
        } else {
            showColor = myYellow
        }
        loops.pause(250)
    }
})
```

## 참고 항목

[`||wheel||`](/reference/rgb/wheel)