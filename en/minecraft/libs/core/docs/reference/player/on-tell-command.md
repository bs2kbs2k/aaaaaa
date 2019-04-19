# on Tell Command

Runs code when another player whispers you a certain message.

```sig
player.onTellCommand("jump", () => {

});
```

## Parameters

* **command**: the chat keyword that will be associated with this command (`*` for all messages), eg: "jump"
* **handler**: code to run when the keyword is whispered to the current player

## Example

Displays a greeting message when another player whispers "hi".

```blocks
player.onTellCommand("hi", () => {
    player.say("Hi, my name is " + player.name())
})
```

## See Also

[say](/reference/player/say), [tell](/reference/player/tell), [on-chat-command](/reference/player/on-chat-command), [name](/reference/player/name)