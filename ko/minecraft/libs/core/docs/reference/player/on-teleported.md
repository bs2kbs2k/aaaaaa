# on Teleported

Runs code when the current player gets teleported.

```sig
player.onTeleported(() => {

});
```

## 매개 변수

* **handler**: code to run when the player gets teleported

## 예시

Adds a text effect in the game chat when you teleport.

```blocks
player.onTeleported(() => {
    player.say("Zoooooom!");
});
```