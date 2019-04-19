# Blinky

Flash the LEDs every one second.

```blocks
loops.forever(() => {
    pins.D13.digitalWrite(false)
    loops.pause(500)
    pins.D13.digitalWrite(true)
    loops.pause(500)
})
```