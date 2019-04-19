# Volcanoes - Part 1

Students build different sized volcanoes with different forces and predict the effects on land that each volcano will have.

## Learning objectives

Play with the parameters such as height, width, and amount of lava to predict and test the effects of different sized volcanoes on the earth around it.

## ~ hint

#### Applicability

**Skill areas**: Science, Earth, Impacts, Hazards

**Ages**: 9-11 yrs old

**Grade level**: 4th, 5th, and 6th

## ~

## Guiding ideas

Understanding the relationship between natural hazards, like volcanoes, and their effects on the world. Treat this as a simulation, not a direct representation.

#### Next Generation Science Standards:

* [4-ESS3-2 Earth and Human Activity](https://www.nextgenscience.org/pe/4-ess3-2-earth-and-human-activity) > "Generate and compare multiple solutions to reduce the impacts of natural Earth processes on humans."

## 학생 학습 활동

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*. This is the first part of the *Volcanoes Lesson* plan and should be followed by [part 2](/lessons/volcano-part2).

이 활동은 2개의 부분으로 이루어져 있습니다.:

* [Research and understand different types of volcanoes](#research-and-understand-different-types-of-volcanoes)
* [Build a volcano in Minecraft using code](#build-a-volcano-in-minecraft-using-code)

### Research and understand different types of volcanoes

Using books, the Internet, or other pre-prepared materials, have your students research the 4 different types of volcanoes; cinder cone, composite, shield, and lava domes. Have them look specifically at the shapes of each volcano. For example, one website is: [4 Types of Volcanoes According to Shape](https://owlcation.com/stem/4-Different-Types-of-Volcanoes-Cinder-Cones-Lava-Domes-Shield-and-Composite-Volcanoes).

Have each student fill in a [Volcano Worksheet #1](/lessons/volcano/worksheet1). You can lead this as either a class activity or an individual assignment.

### Build a volcano in Minecraft using code

Based on the drawings that the students did using their [Volcano Worksheet #1](/lessons/volcano/worksheet1), have them design a chat command that will create the mountainous shape of the volcano.

For example, the code may look like this:

```blocks
player.onChat("volcanoes", function () {
    player.runChatCommandWithArguments("cindercone", "20 10")
})
player.onChat("cindercone", function (width, height) {
    for (let index = 0; index <= height; index++) {
        blocks.fill(
        blocks.block(Block.Gravel),
        positions.create(index - width, index, index - width),
        positions.create(width - index, index, width - index),
        FillOperation.Replace
        )
    }
})
```

It is recommended that you walk students through the general algorithm of creating a pyramid first. Then, allow them to play with the parameters and mathematical equations to get the proper shape.

For lava, students can either programmatically place the lava in the center, or they can go through and add lava by hand. To create explosions, have students create their volcano primarily from obsidian then lay TNT with a redstone trail coming to an exit on the side of the volcano. Cover the TNT with gravel, then with lava, and when you’re ready for an explosion, ignite the redstone trail.

Lead students through a discussion as to why it is better to code a volcano than build it by hand. The reasons for this are:

1. In [Part 2](/lessons/volcano-part2), you will be testing the effects of different volcanoes, requiring you to re-create volcanoes with different parameters.
2. To truly test the effects on different parts of Earth, it is important to be able to place the volcano in different areas (on top of mountains, in the water, underground) to see the different effects.

## Performance Expectations

#### Intended outcomes:

* Understanding of the different sizes and shapes of different volcano types.
* Learning how to programmatically build large structures.
* Understanding the importance of parameters.

## 자료

[Volcanoes - Part 2](/lessons/volcano-part2)

[화산 활동지 #1](/lessons/volcano/worksheet1)