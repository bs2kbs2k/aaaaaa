# run Chat Command

Runs a chat command in your code that was already created using [`||player:on chat command||`](/reference/player/on-chat-command).

```sig
player.runChatCommand("jump");
```

## 매개 변수

* **command**: the chat command to run, like: "jump".

## 예시

Let's say you have a chat command in your project that makes your agent move forward and place a block:

```blocks
player.onChat("placeforward", function () {
        agent.move(SixDirection.Forward, 1);
        agent.place(SixDirection.Back);
});
```

You can reuse this chat command in other parts of your code to have your agent build a row:

```blocks
player.onChat("row", function () {
    agent.teleportToPlayer();
    for (let i = 0; i < 5; i++) {
        player.runChatCommand("placeforward");
    }
});
```

## 참고 항목

[`||player:run chat command with args||`](/reference/player/run-chat-command-with-args), [`||player:on chat command||`](/reference/player/on-chat-command)