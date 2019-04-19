# on Arrow Shot

Runs code when the current player shoots an arrow.

```sig
player.onArrowShot(() => {

});
```

## 매개 변수

* **handler**: code to run when the player shoots an arrow

## 예시

Warn your friends that you just shot an arrow.

```blocks
player.onArrowShot(() => {
    player.say("Watch out!");
});
```