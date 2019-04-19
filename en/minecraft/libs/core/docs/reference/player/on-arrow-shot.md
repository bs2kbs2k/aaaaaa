# on Arrow Shot

Runs code when the current player shoots an arrow.

```sig
player.onArrowShot(() => {

});
```

## Parameters

* **handler**: code to run when the player shoots an arrow

## Example

Warn your friends that you just shot an arrow.

```blocks
player.onArrowShot(() => {
    player.say("Watch out!");
});
```