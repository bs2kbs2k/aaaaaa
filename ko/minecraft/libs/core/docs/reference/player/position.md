# position

Returns the world position of the current player. The world position is the current location (absolute coordinates) of the player in the game world.

```sig
player.position();

```

## 예시

Display your world position in the game chat. Make a chat command called `myposition` to [say](/reference/player/say) your location. Join the `My current position is:` string with your **position**.

```blocks
player.onChat("myposition", function () {
    player.say("My current position is: " + player.position());
});
```

## 참고 항목

To learn how positions work, see [positions](/reference/positions).