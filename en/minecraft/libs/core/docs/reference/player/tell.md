# tell

Whispers a message to targets. Only the target or targets you connect will see the message.

```sig
player.tell(mobs.target(TargetSelectorKind.AllPlayers), "Hi!");
```

## Parameters

* **target**: a selector of entities
* **message**: the text to whisper, eg: "Hi!"

## Example

Whisper "Hi!" to all players. Connect a [mob target](/reference/mobs/selectors/target) with `all players (@a)` and the `Hi!` string to **tell**.

```blocks
player.tell(mobs.target(TargetSelectorKind.AllPlayers), "Hi!");
```

## See Also

[say](/reference/player/say)