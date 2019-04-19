# on Bounced

Runs code when the current player bounces on a slime.

```sig
player.onBounced(() => {

});
```

## 매개 변수

* **handler**: code to run when the player bounces

## 예시

Adds a text effect in the game chat when you bounce around.

```blocks
player.onBounced(() => {
    player.say("Boing!")
});
```