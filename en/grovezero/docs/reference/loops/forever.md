# forever

Run a part of the program in the background and keep running it over again.

```sig
loops.forever(() => {
})
```

The code you have in a `||forever||` loop will run and keep repeating itself the whole time your program is active. Code in other parts of your program won't stop while your `||forever||` loop is running. This includes other `||forever||` loops and the [`||run in background||`](/reference/control/run-in-background) block.

## Parameters

* **a**: the code to keep running over and over again.

## Example

Blink the LED on Grove Zero core board.

```blocks
loops.forever(() => {
    pins.D13.digitalWrite(false)
    loops.pause(500)
    pins.D13.digitalWrite(true)
    loops.pause(500)
})
```

## See also

[`||while||`](/blocks/loops/while), [`||repeat||`](/blocks/loops/repeat), [`||run in background||`](/reference/control/run-in-background)