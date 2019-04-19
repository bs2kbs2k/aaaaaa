# to String

Make a string that describes a position in text you can read.

```sig
positions.create(0, 0, 0).toString();
```

Sometimes it's nice to represent a position as a string. You can display it in the game chat, or send it as an argument to a chat command.

## 예시

Display the current player's position in the game chat when you type the "where" command.

```blocks
player.onChat("where", function () {
    player.say("My current position is:");
    player.say(player.position().toString());
});
```