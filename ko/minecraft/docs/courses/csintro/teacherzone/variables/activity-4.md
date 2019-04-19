# Activity: Wordsmith

## Challenges

### Challenge 1 - Display a '+' Sign to Make the Action Look Like a Math Problem

```blocks
let word2 = ""
let word1 = ""
let Starting_World_Position: Position = null
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.add(
    Starting_World_Position,
    positions.create(0, 30, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    "+",
    blocks.block(Block.PlanksBirch),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, -10)
    ),
    CompassDirection.South
    )
    blocks.print(
    word2,
    blocks.block(Block.RedstoneLamp),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    "" + word1 + word2,
    blocks.block(Block.RedstoneBlock),
    positions.add(
    Starting_World_Position,
    positions.create(0, 5, 0)
    ),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

### Challenge 2 - Add a Line to Finish the Math Equation Look

```blocks
let word2 = ""
let word1 = ""
let Starting_World_Position: Position = null
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    blocks.block(Block.RedstoneOre),
    positions.add(
    Starting_World_Position,
    positions.create(0, 30, 0)
    ),
    CompassDirection.South
    )
    blocks.print(
    "+",
    blocks.block(Block.PlanksBirch),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, -10)
    ),
    CompassDirection.South
    )
    blocks.print(
    word2,
    blocks.block(Block.RedstoneLamp),
    positions.add(
    Starting_World_Position,
    positions.create(0, 20, 0)
    ),
    CompassDirection.South
    )
    blocks.fill(
    blocks.block(Block.PlanksBirch),
    positions.add(
    Starting_World_Position,
    positions.create(0, 15, -10)
    ),
    positions.add(
    Starting_World_Position,
    positions.create(0, 15, 60)
    ),
    FillOperation.Replace
    )
    blocks.print(
    "" + word1 + word2,
    blocks.block(Block.RedstoneBlock),
    positions.add(
    Starting_World_Position,
    positions.create(0, 5, 0)
    ),
    CompassDirection.South
    )
})
word1 = "rail"
word2 = "road"
```

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Flying Letters

```blocks
let RandomLetter = 0
let Alphabet = ""
player.onTravelled(TravelMethod.Fly, function () {
    Alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    RandomLetter = Math.randomRange(0, 25)
    blocks.print(
    Alphabet.charAt(RandomLetter),
    blocks.block(Block.YellowGlazedTerracotta),
    positions.create(-5, 2, 0),
    CompassDirection.West
    )
})
```

### Experiment 2 - Chopping Up Sentences

```blocks
let wordEnd = 0
let wordStart = 0
let RandomWord = 0
let Sentence = ""
player.onTravelled(TravelMethod.Fly, function () {
    Sentence = "Which word will it choose?"
    RandomWord = Math.randomRange(0, 4)
    if (RandomWord == 0) {
        wordStart = 0
        wordEnd = 5
    } else if (RandomWord == 1) {
        wordStart = 6
        wordEnd = 4
    } else if (RandomWord == 2) {
        wordStart = 11
        wordEnd = 4
    } else if (RandomWord == 3) {
        wordStart = 16
        wordEnd = 2
    } else {
        wordStart = 19
        wordEnd = 6
    }
    blocks.print(
    Sentence.substr(wordStart, wordEnd),
    blocks.block(Block.GoldBlock),
    positions.create(-5, 2, 0),
    CompassDirection.West
    )
})
```

## Reference examples

### Constructive examples:

* [에이전트 벽 만들기](examples/agent-wall)
* [에이전트 타워 만들기](examples/agent-tower)
* [메가 점프](/examples/mega-jump)
* [토끼 침공](/examples/rabbit-invasion)

### Destructive examples:

* [신뢰의 도약](/tutorials/leap-of-faith)
* [스플리프](examples/spleef) 
* [TNT 스플리프](examples/tnt-spleef)