# Activity: The Linked Wall

In this activity, you will link events. You will build a wall of glass. When you break a glass block, a new diamond block will randomly appear in the wall. Then, if you break the new diamond block, orange wool will randomly appear.

![glass wall turns to diamond then to orange wool](/static/courses/csintro/events/act4-main-pic.jpg)

## Do the activity

### Get a jump start

The next lesson, [Lesson 3](/courses/csintro/coordinates), is about coordinates. Variables are taught in [Lesson 4](/courses/csintro/variables). This activity uses both, but don't be scared. This activity gives you everything you need to know in a very simple way, so that at the end you can examine these new concepts in the code but do not need any upfront knowledge of them.

The focus remains on events, but in order to make the activity a bit more interesting, these instructions need to include these other concepts.

1. Select and Copy the following code (use `Control` + `C`).

```typescript
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
```

2. In the block editor, change to the JavaScript view.

![javascript view](/static/courses/csintro/events/act4-javascript.png)

3. Paste the code into this window (use `Control` + `V`).

![javascript view pasted](/static/courses/csintro/events/act4-javascript-pasted.png)

4. Switch back to the blocks view.

You should now have all the coordinates, and variables to store those coordinates in. Enter **position** in the chat window to store the coordinates you will need. With that done, let's get started.

5. From `||player:Player||`, drag out a `||player:on chat||` event handler.

6. Change `"jump"` to `"wall"`.

Here you will build your wall using the positions or coordinates you gather.

7. From `||blocks:BLOCKS||`, place a `||blocks:fill with||` block inside `||player:on chat command "wall"||`.

Let's adjust some things.

8. Fill with glass instead of grass.

9. From `||variables:VARIABLES||`, put `||variables:from_position||` into `from` in the `||blocks:fill with||` block.

10. Next, from `||variables:VARIABLES||`, put `||variables:to_position||` into `to` in the `||blocks:fill with||` block.

This should be enough to build your wall. You can test it out if you wish. You will need to first type **position** in the chat window and press `Enter`. Next, type **wall** in the chat window and press `Enter`.

```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
player.onChat("wall", function () {
    blocks.fill(
    blocks.block(Block.Glass),
    from_position,
    to_position,
    FillOperation.Replace
    )
})
```

Next, you need to react when blocks are broken.

11. From `||blocks:BLOCKS||`, drag a `||blocks:on broken||` block onto the Workspace.

12. Change `grass` to `glass`.

13. From `||blocks:BLOCKS||`, put a `||blocks:place||` block into `||blocks:on broken||`.

14. Change `grass` to `diamond`.

```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
player.onChat("wall", function () {
    blocks.fill(
    blocks.block(Block.Glass),
    from_position,
    to_position,
    FillOperation.Replace
    )
})
blocks.onBlockBroken(blocks.block(Block.Glass), function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.create(0, 0, 0))
})
```

Now all you need to do is fix the position code.

15. From `||position:POSITION||`, place `||position:pick random position||` into the `||blocks:diamond||` block.

16. From `||variables:VARIABLES||`, put `||variables:from_position||` into `from` in this block.

17. From `||variables:VARIABLES||`, put `||variables:to_position||` into `to` in this block.

It would look like this...

```block
let to_position: Position = null
let from_position: Position = null
blocks.onBlockBroken(blocks.block(Block.Glass), function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
        from_position,
        to_position
    ))
})
```

Now you can just duplicate this block and change a few things to finish.

18. Duplicate `||blocks:on glass broken||`.

19. Change `glass` to `diamond`.

20. Then change `||blocks:place diamond||` to `||blocks:place orange wool||`.

Again, to use this code, enter a world. First, type **position** into the chat window. Next, type **wall** into the chat window. Finally, start breaking blocks and see what happens.

```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
blocks.onBlockBroken(blocks.block(Block.Glass), function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
})
blocks.onBlockBroken(blocks.block(Block.DiamondBlock), function () {
    blocks.place(blocks.block(Block.OrangeWool), positions.random(
    from_position,
    to_position
    ))
})
player.onChat("wall", function () {
    blocks.fill(
    blocks.block(Block.Glass),
    from_position,
    to_position,
    FillOperation.Replace
    )
})
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
```

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Add More Blocks When Glass Is Broken

The original code is good, but let's add even more blocks if glass is broken. How could you add three diamond blocks when glass is broken instead of just one diamond block?

There a few ways to do this.

You will need to:

1. Look at the original code to see how diamond blocks are created.
2. Find a way to do that two more times.

### Challenge 2 - Instead of Orange Wool, Create Chickens!

The original code creates orange wool blocks when diamond blocks are broken. Can you change this so 10 chickens are spawned when diamond blocks are broken?

You will need to:

1. Change the code that is triggered when a diamond block is broken.
2. Spawn 10 chickens (you could use a repeat loop or 10 of the same blocks).

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - The Colosseum

This code is huge! Have some fun!

Can you figure out how to start it?

Here's how this code works: When you kill one of the animals or monsters, they are respawned into the score box above their name. This works with an `||mobs:on animal killed||` event. That is your scoreboard! If you kill all the monsters and animals, all of them will be up above their names in their cages at the end of the fight.

There are a lot of functions in this code. [Functions](/types/function) are good way to make bigger code more readable and organized.

What changes could you make to this? Could you change the animals? Could you change the words on the walls? You might try to add in some villagers on top of the colosseum to give it a crowd.

![Colosseum - ground view](/static/courses/csintro/events/colosseum1.jpg)

![Colosseum - sky view](/static/courses/csintro/events/colosseum2.jpg)