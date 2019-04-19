# Stories come to life

Students re-create a scene from a book they are reading in Minecraft with interactive components using code.

## Learning objectives

Use several sections of code to animate life with different interaction blocks Re-create a scene using builders and commands.

## ~ hint

#### Applicability

**Skill areas**: ELA, Literature, Speaking, Presenting, Reading

**Ages**: 9-11 yrs old

**Grade level**: 4th and 5th

## ~

## Guiding ideas

Determine the main ideas and supporting details of a text. Use multimedia components (e.g., graphics, sound) and visual displays in presentations when appropriate to enhance the development of main ideas or themes.

#### Related Common Core ELA standards:

* [CCSS.ELA-LITERACY.SL.4.2](http://www.corestandards.org/ELA-Literacy/SL/4/#CCSS.ELA-Literacy.SL.4.2)
* [CCSS.ELA-LITERACY.SL.4.5](http://www.corestandards.org/ELA-Literacy/SL/4/#CCSS.ELA-Literacy.SL.4.5)
* [CCSS.ELA-LITERACY.SL.5.2](http://www.corestandards.org/ELA-Literacy/SL/5/#CCSS.ELA-Literacy.SL.5.2)
* [CCSS.ELA-LITERACY.SL.5.5](http://www.corestandards.org/ELA-Literacy/SL/5/#CCSS.ELA-Literacy.SL.5.5)

## 학생 학습 활동

This activity requires students to have the *Code Connection* app open and running with their Minecraft Education Edition.

이 활동은 2개의 부분으로 이루어져 있습니다.:

* [Recreate a scene in Minecraft](#recreate-a-scene-in-minecraft)
* [Make the scene interactive](#make-the-scene-interactive)

### Recreate a scene in Minecraft

Have students choose a scene from the book they are reading.

**OPTIONAL**: Have students draw the scene on paper first and have it approved by you. On the back of their drawing, have students write a short list of actions that happened during that scene.

Using either code or drawing by hand, have students create a scene from a book they are reading in Minecraft. For example, to make three houses in a row, you could use the following code:

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

Make sure that students spend time constructing the scene to look like the scene from the book.

### Make the scene interactive

Have students come up with a list of actions that happened in the scene they chose. For example, if students choose a scene from *Alice in Wonderland*, they might decide to use the scene where Wonderland creatures started erasing Alice’s path behind her.

Have students match actions in the book to the actions in Minecraft that they can create in code. Using the same example from *Alice in Wonderland*, have students change blocks that the player walks on to obsidian so that the pathway is erased:

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.place(blocks.block(Block.Obsidian), positions.create(0, -1, 0))
})
```

## Performance expectations

#### Intended outcomes:

* Understanding how to explore story ideas and translate them to interactive presentations.
* Engaging in planning, designing, and coding to re-create a story.

## 자료

[Story ending](/lessons/story-ending)