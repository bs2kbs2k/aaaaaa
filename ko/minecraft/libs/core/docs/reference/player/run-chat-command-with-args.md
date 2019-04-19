# run Chat Command With Arguments

Runs a chat command in your code with arguments. The argument is a string used by the code inside your [`||player:run chat command||`](/reference/player/run-chat-command) code block.

```sig
player.runChatCommandWithArguments("jump", "5");
```

## 매개 변수

* **command**: the chat command to run, like: "jump"
* **arg**: a string containing all the arguments you wish to give to the chat command

## 예시

Let's say you have a chat command in your project that makes your agent build a row of blocks of variable length:

```blocks
player.onChat("row", function (length) {
    for (let i = 0; i < length; i++) {
        agent.move(SixDirection.Forward, 1);
        agent.place(SixDirection.Back);
    }
})
```

You can reuse this chat command in other parts of your code to build a square, for example:

```blocks
player.onChat("square", function () {
    agent.teleportToPlayer()
    agent.move(SixDirection.Forward, 1)
    for (let i = 0; i < 4; i++) {
        player.runChatCommandWithArguments("row", "5")
        loops.pause(5000)
        agent.turn(TurnDirection.Left);
        agent.move(SixDirection.Forward, 1)
        agent.move(SixDirection.Left, 1)
    }
});
```

The new chat command named `square` uses the `row` chat command to place rows of `5` blocks. The `row` command is repeated 4 times to make a square that is 5 blocks wide. Each time your agent places a row of blocks and is then told to **turn** and **move** to make the next side of the square.

## 참고 항목

[`||player:run chat command||`](/reference/player/run-chat-command), [`||player:on chat command||`](/reference/player/on-chat-command)