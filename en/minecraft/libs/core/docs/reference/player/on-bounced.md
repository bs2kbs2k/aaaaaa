# on Bounced

Runs code when the current player bounces on a slime.

```sig
player.onBounced(() => {

});
```

## Parameters

* **handler**: code to run when the player bounces

## Example

Adds a text effect in the game chat when you bounce around.

```blocks
player.onBounced(() => {
    player.say("Boing!")
});
```