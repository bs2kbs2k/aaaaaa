# 일시 중지

Pause a part of the program for some number of milliseconds.

```sig
loops.pause(100)
```

When code in a block comes to a `||pause||`, it will wait the amount of time you tell it to. Code in blocks like `||forever||` and `||run in background||` will keep running while code in some other block is waiting at a `||pause||`.

## 매개 변수

* **ms**: the [number](/types/number) of milliseconds that you want to pause for. So, 100 milliseconds = 1/10 second, and 1000 milliseconds = 1 second.

## 예시

Blink the LED on Grove Zero core board.

```blocks
loops.forever(() => {
    pins.D13.digitalWrite(false)
    loops.pause(500)
    pins.D13.digitalWrite(true)
    loops.pause(500)
})
```

## 참고 항목

[`||while||`](/blocks/loops/while), [`||for||`](/blocks/loops/for), [`||forever||`](/reference/loops/forever)