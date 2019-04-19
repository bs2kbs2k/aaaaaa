# run In Background

Run some other code at the same time that your main program code runs.

```sig
loops.runInBackground(function () {

})
```

Sometimes you want your program to work on more than one thing at a time. The main part of your program is always put in [`||loops:on start||`](/blocks/on-start). But, you can also put some other part of your program in `||loops:run in background||`. This is useful when you want your program to keep doing important things and you don't want to wait for some other actions to happen first.

## Parameters

* **handler**: the code to run in the background.

## Example

Have the agent build a tower while you wait for the player to type the "jump" command.

```blocks
loops.runInBackground(function () {
    for (let i = 0; i < 6; i++) {
        for (let j = 0; j < 4; j++) {
            agent.place(SixDirection.Back)
            agent.turn(TurnDirection.Right)
            agent.move(SixDirection.Forward, 1)
            loops.pause(2000)
        }
        agent.move(SixDirection.Up, 1)
    }
})
player.onChat("jump", function () {
    player.teleport(positions.create(0, 0, 100))
})
```

## See also

[forever](/reference/loops/forever)