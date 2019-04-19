# xp

Give experience points to players.

```sig
gameplay.xp(10, mobs.target(TargetSelectorKind.LocalPlayer));
```

Experience points you give to players with `||gameplay:xp||` will show up in their experience bar only when they are playing in survival mode. The experience you give might take a little time to show up in the progress bar. If it doesn't show, the player might need to open and close the chat.

## Parameters

* **amount**: the number of experience points to give, such as: `10`
* **target**: a selector to for the players who will get the experience

## Example

Give experience to the local player every time they sprint.

```blocks
player.onTravelled(TravelMethod.Sprint, () => {
    gameplay.xp(1, mobs.target(TargetSelectorKind.LocalPlayer))
})
```