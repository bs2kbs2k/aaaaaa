# The Gold Rush

Students re-create the California gold rush by creating mountains hidden with gold.

## Learning objectives

Play with parameters to make mountains full of realistic amounts of gold. Re-create a scene around a mountain to sustain mining for gold.

## ~ hint

#### Applicability

**Skill areas**: Science, Earth, Social Studies, Natural

**Ages**: 9-11 yrs old

**Grade level**: 4th

## ~

## Guiding ideas

Understanding the relationship between natural hazards, like volcanoes, and their effects on the world. Treat this as a simulation, not a direct representation.

#### Related Common Core ELA standards:

* [CCSS.ELA-LITERACY.RI.4.1](http://www.corestandards.org/ELA-Literacy/RI/4/1/)
* [CCSS.ELA-LITERACY.RI.4.3](http://www.corestandards.org/ELA-Literacy/RL/4/3/)
* [CCSS.ELA-LITERACY.RI.4.7](http://www.corestandards.org/ELA-Literacy/RL/4/7/)

## Student activities

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*.

This activity consists of 2 parts:

* [Programmatically create a mountain with gold](#programmatically-create-a-mountain-with-gold)
* [Survive mining the area in Survival Mode](#survive-mining-the-area-in-survival-mode)

### Programmatically create a mountain with gold

Have students first decide on the width and height of their mountain. If you want to keep it consistent, you can use an algorithm like this to have everyone create a mountain 10 blocks high and 40 blocks wide:

```blocks
player.onChat("mountain", function () {
    for (let index = 0; index <= 10; index++) {
        blocks.fill(
            blocks.block(Block.Gravel),
            positions.create(index - 20, index, index - 20),
            positions.create(20 - index, index, 20 - index),
            FillOperation.Replace
        )
    }
})
```

Have students then place a gold block somewhere randomly within their mountain:

```blocks
let goldheight = 0
player.onChat("gold", function () {
    goldheight = Math.randomRange(0, 10)
    blocks.fill(
        blocks.block(Block.GoldBlock),
        positions.create(goldheight - 20, goldheight, goldheight - 20),
        positions.create(20 - goldheight, goldheight, 20 - goldheight),
        FillOperation.Replace
    )
})
```

To make each mountain even more random, have students random place 0-500 gold blocks in each mountain:

```blocks
let goldheight = 0
player.onChat("mountain", function () {
    for (let index = 0; index <= 10; index++) {
        blocks.fill(
            blocks.block(Block.Gravel),
            positions.create(index - 20, index, index - 20),
            positions.create(20 - index, index, 20 - index),
            FillOperation.Replace
        )
    }
})
player.onChat("makeGold", function () {
    player.runChatCommand("mountain")
    for (let i = 0; i < Math.randomRange(0, 500); i++) {
        player.runChatCommand("gold")
    }
})
player.onChat("gold", function () {
    goldheight = Math.randomRange(0, 10)
    blocks.fill(
        blocks.block(Block.GoldBlock),
        positions.create(goldheight - 20, goldheight, goldheight - 20),
        positions.create(20 - goldheight, goldheight, 20 - goldheight),
        FillOperation.Replace
    )
})
```

### Survive mining the area in Survival Mode

Have students conduct research on what was needed to survive the mining days in California. For example, water, homes, agriculture, etc.

The goal for the students is to mine as much gold while surviving only in a small area (around the mountain). Students should put together a "Survival Guide" prior to beginning their Minecraft play. You can use the [Gold Mine Worksheet](/lessons/goldmine/worksheet), or design one of your own. There should be references based on informational text for each survival guide.

Give students one entire class period to survive living as a miner. Students should switch into **Survival Mode** and explore the mountain, creating mines and towns that can prosper if the mountain has enough gold. If the student's player dies, they must abandon their mine and can join another person’s mountain to help.

Lead a class discussion on why certain people were able to survive and why certain people found more gold than others. Discuss how preparation and randomness affect how some students fair better than others.

## Performance Expectations

#### Intended outcomes:

* Understanding informational text and how it informs the activity.
* Learning randomness and its effects on outcomes.
* Compare and contrast randomness of gold in Minecraft and gold in the real world.

## Resources

[Gold Mine Worksheet](/lessons/goldmine/worksheet)