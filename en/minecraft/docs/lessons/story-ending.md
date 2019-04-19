# Re-imagine stories

Students re-imagine the ending to one of their favorite stories in Minecraft.

## Learning objectives

Play with different code interactions to make a story come to life.

## ~ hint

#### Applicability

**Skill areas**: ELA, Speaking, Presenting, Predicting, Inferring

**Ages**: 7-10 yrs old

**Grade level**: 3rd and 4th

## ~

## Guiding ideas

Refer to details and examples in a text when explaining what the text says explicitly and when drawing inferences from the text.

#### Related Common Core ELA standards:

* [CCSS.ELA-LITERACY.RL.3.6](http://www.corestandards.org/ELA-Literacy/RL/3/#CCSS.ELA-Literacy.RL.3.6)
* [CCSS.ELA-LITERACY.RL.4.1](http://www.corestandards.org/ELA-Literacy/RL/4/#CCSS.ELA-Literacy.RL.4.1)

## Student activities

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*.

This activity consists of 3 parts:

* [Re-write the ending to a Book](#re-write-the-ending-to-a-book)
* [Build the imaginary World in Minecraft](#build-the-world-in-minecraft)
* [Make the world interactive](#make-the-world-interactive)

### Re-write the ending to a book

Have students spend time re-writing the ending to a book they are reading. You can have all students do this for the same book, or have each choose their own book/story. Students should spend time imagining how the ending would be different with one major change to the final chapter.

### Build the world in Minecraft

Have students draw the scene on paper first and have it approved by you. On the back of their drawing, have students write a short list of actions that happened during that scene, referring to the writing they did in the [Storyline](/lessons/storyline) lesson.

Using either code or creating the scene by hand, have students create a scene from a book they are reading in Minecraft. For example, to make three houses in a row, you could use the following code:

```blocks
player.onChat("makescene", function () {
    player.runChatCommandWithArguments("house", "3 5")
    player.runChatCommandWithArguments("house", "7 5")
    player.runChatCommandWithArguments("house", "11 5")
})

player.onChat("house", function (x, y) {
    blocks.fill(
    blocks.block(Block.PlanksSpruce),
    positions.create(x - 3, 0, y - 5),
    positions.create(x, 5, y),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.Air),
    positions.create(x - 2, 1, y - 4),
    positions.create(x - 1, 4, y - 1),
    FillOperation.Replace
    )
})
```

Or you could make each house individually:

```blocks
player.onChat("jump", function () {
    player.runChatCommand("house1")
    player.runChatCommand("house2")
    player.runChatCommand("house3")
})

player.onChat("house1", function () {
    blocks.fill(
        blocks.block(Block.PlanksSpruce),
        positions.create(0, 0, 0),
        positions.create(3, 5, 5),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Air),
        positions.create(1, 1, 1),
        positions.create(2, 4, 4),
        FillOperation.Replace
    )
})

player.onChat("house2", function () {
    blocks.fill(
        blocks.block(Block.PlanksSpruce),
        positions.create(4, 0, 0),
        positions.create(7, 5, 5),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Air),
        positions.create(3, 1, 1),
        positions.create(6, 4, 4),
        FillOperation.Replace
    )
})

player.onChat("house3", function () {
    blocks.fill(
        blocks.block(Block.PlanksSpruce),
        positions.create(8, 0, 0),
        positions.create(11, 5, 5),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Air),
        positions.create(9, 1, 1),
        positions.create(10, 4, 4),
        FillOperation.Replace
    )
})
```

Make sure that students spend time making the scene look like the scene from the book.

### Make the world interactive

Have students come up with a list of actions that happened during the scene that they chose. For example, if students wanted to make a character represent extreme winter, then when the player walks, everything should turn to ice:

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.place(blocks.block(Block.PackedIce), positions.create(0, -1, 0))
})

player.onTravelled(TravelMethod.SwimLava, () => {
    blocks.fill(
        blocks.block(Block.PackedIce),
        positions.create(-1, -1, -1),
        positions.create(1, 0, 1),
        FillOperation.Replace
    )
})
```

## Performance expectations

#### Intended outcomes:

* Understanding how to explore story ideas and translate them to interactive presentations.
* Engaging in planning, designing, and coding to re-create a story.
* Predict what would happen within a storyline given one minor change in the final chapter of a book.

## Resources

[Storyline](/lessons/storyline)