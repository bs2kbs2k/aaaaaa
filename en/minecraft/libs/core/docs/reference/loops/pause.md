# pause

Pause a part of the program for some number of milliseconds.

```sig
pause(400)
```

When code in a block comes to a `||loops:pause||`, it will wait the amount of time you tell it to. Code in blocks like `||loops:forever||` and `||loops:run in background||` will keep running while code in some other block is waiting at a `||loops:pause||`.

## Parameters

* **ms**: the [number](/types/number) of milliseconds that you want to pause for. So, 100 milliseconds = 1/10 second, and 1000 milliseconds = 1 second.

## Example

Place `20` sandstone blocks at one second intervals.

```blocks
for (let x = 0; x <= 20 - 1; x++) {
    blocks.place(blocks.block(Block.Sandstone), positions.create(0, x * 2, 0))
    loops.pause(1000)
}
```

## See also #seealso

[while](/blocks/loops/while), [for](/blocks/loops/for), [forever](/reference/loops/forever)