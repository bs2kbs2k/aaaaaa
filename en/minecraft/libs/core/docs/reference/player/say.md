# say

Posts a message to the game chat.

```sig
player.say("Hi!");
```

## Parameters

* **message**: the message to display in the chat, eg: "Hi!"

## Example

Display a warning message when a chicken dies. The **say** block is run when the [mobs:on Mob Killed](/reference/mobs/on-mob-killed) event happens.

```blocks
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), () => {
    player.say("Be nice to the chickens!")
})
```

## See Also

[`||player:tell||`](/reference/player/tell)