# push State

Push the builder's current **state** onto the state **stack**.

```sig
builder.pushState();
```

The **state** is all the important details about the builder. This includes all these things:

* Position (where the builder is at right now)
* Orientation (direction the builder is facing)
* Path (where the builder has traveled)
* Last marked position (the builder's **mark**)
* Origin (the position set for the builder's origin)

A **stack** is a way of saving information by placing new details on top of old details. The **state** information put on the **stack** using any earlier `||builder:push state||` is still there. You can restore the builder's details to the way were before by ***popping*** the information from the stack. This removes the details from the stack and gives it back to the builder. The builder will have the settings it had when you ***pushed*** them on the stack.

This is useful when you make complex structures and you want to put the builder back to the way it was before. You don't have to remember all the details, just pop them back to the builder.

## Example

Use builder states to create a structure shaped like a 'Y'.

**First:** The builder creates a vertical pillar and saves its state at the top with `||builder:push state||`.

**Then:** The builder creates the first arm of the structure.

**Finally:** The saved state is restored using `||builder:pop state||` to make the second arm.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
builder.mark();
builder.move(SixDirection.Up, 5);
builder.line(blocks.block(Block.DiamondBlock));
builder.mark();
builder.pushState();
builder.shift(0, 5, 5);
builder.line(blocks.block(Block.GoldBlock));
builder.popState();
builder.shift(0, 5, -5);
builder.line(blocks.block(Block.RedstoneBlock));
```

## See Also

[`||builder:pop state||`](/reference/builder/pop-state)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).