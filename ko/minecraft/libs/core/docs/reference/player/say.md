# say

Posts a message to the game chat.

```sig
player.say("Hi!");
```

## 매개 변수

* **message**: the message to display in the chat, eg: "Hi!"

## 예시

Display a warning message when a chicken dies. The **say** block is run when the [mobs:on Mob Killed](/reference/mobs/on-mob-killed) event happens.

```blocks
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), () => {
    player.say("Be nice to the chickens!")
})
```

## 참고 항목

[`||player:tell||`](/reference/player/tell)