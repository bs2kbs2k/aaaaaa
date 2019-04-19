# teleport

Teleports the current player to another position.

```sig
player.teleport(positions.create(0,0,0));
```

## Parameters

* **to**: the destination position

## Examples

### Super jump

Teleport the player `100` blocks up when the `jump` command is typed in the chat.

```blocks
player.onChat("jump", function () {
    player.teleport(positions.create(0,100,0));
});
```

### Go anywhere

Teleport the player anywhere in two dimensions from the current location. The player goes to a random location `50` blocks North or South, and `50` blocks East or West. The player moves when the `goany` command is typed in the chat.

```blocks
player.onChat("goany", function () {
     player.teleport(positions.random(
       positions.create(-50, 0, 50),
       positions.create(50, 0, -50)));
});
```

## See Also

[on-chat-command](/reference/player/on-chat-command), [positions](/reference/positions), [teleport (mob)](/reference/mobs/teleport-to-position)