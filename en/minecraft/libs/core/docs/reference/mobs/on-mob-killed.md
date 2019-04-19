# on Mob Killed

Run some code when a certain kind of creature is killed.

```sig
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), () => {

});
```

## Parameters

* **mob**: the type of creature
* **handler**: the code you want to run when a creature you chose in **mob** is killed

## Example

Display a warning message when a chicken dies.

```blocks
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), () => {
    player.say("Be nice to the chickens! Baaack!")
})
```

See also

[`||mobs:kill||`](/reference/mobs/kill)