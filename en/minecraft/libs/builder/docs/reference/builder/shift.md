# shift

Move the builder in three different directions at once.

```sig
builder.shift(1, 1, 1);
```

## Parameters

* **forward**: the number of blocks by which to move forward, like: 2, or -1 to go backward
* **up**: the number of blocks by which to move up, like: 1, or -4 to go down
* **left**: the number of blocks by which to move left, such as: 5 or -3 to go right

## Example

Move the builder to the opposite corner of a 5 x 5 x 5 cube shaped space.

```blocks
builder.shift(5, 5, 5);
```

## See Also

[`||builder:move||`](/reference/builder/move)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).