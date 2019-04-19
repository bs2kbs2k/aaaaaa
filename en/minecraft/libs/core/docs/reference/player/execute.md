# execute

Executes a game command as the current player. These are the slash commands ("/") in the chat window.

```sig
player.execute("say hi");
```

## Parameters

* **command**: the slash command to execute (you do not have to put the leading `/`), eg: "say Hi!"

## Example

Executes a slash command to teleport all players to you.

```blocks
player.execute("tp @a ~ ~ ~");
```