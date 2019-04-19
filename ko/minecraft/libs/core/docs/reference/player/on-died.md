# on Died

Runs code when the current player dies.

```sig
player.onDied(() => {

});
```

## 매개 변수

* **handler**: code to run when the current player dies

## 예시

### Make it rain

Make it rain when the player dies.

```blocks
player.onDied(() => {
    gameplay.setWeather(Weather.Rain);
});
```

### Tell everyone goodbye

**Say** a farewell message in chat.

```blocks
player.onDied(() => {
    player.say("I'm gone for now but I'll be back!");
});
```