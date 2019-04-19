# on Teleported

Runs code when the current player gets teleported.

```sig
player.onTeleported(() => {

});
```

## Parameters

* **handler**: code to run when the player gets teleported

## Example

Adds a text effect in the game chat when you teleport.

```blocks
player.onTeleported(() => {
    player.say("Zoooooom!");
});
```