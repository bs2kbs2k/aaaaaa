# execute

Executes a game command as the current player. These are the slash commands ("/") in the chat window.

```sig
player.execute("say hi");
```

## 매개 변수

* **command**: the slash command to execute (you do not have to put the leading `/`), eg: "say Hi!"

## 예시

Executes a slash command to teleport all players to you.

```blocks
player.execute("tp @a ~ ~ ~");
```