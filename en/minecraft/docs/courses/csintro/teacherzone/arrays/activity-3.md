# Activity: Blocks by ID

## Challenges

### Challenge 1 - Randomly Print One of the Stored Blocks

```blocks
let RandomBlock = 0
let Blocks: number[] = []
player.onChat("printblocks", function () {
    for (let index = 0; index <= Blocks.length - 1; index++) {
        RandomBlock = Math.randomRange(0, Blocks.length - 1)
        blocks.place(blocks.blockById(Blocks[RandomBlock]), positions.create(2, 0, index))
    }
})
Blocks = [1, 2, 3, 4, 5]
```

Some blocks might be printed twice because they are chosen randomly.

![Printing a Random Block](/static/courses/csintro/arrays/blockidsrandom.png)

### Challenge 2 - Remove a block and report feedback

```blocks
let RandomBlock = 0
let Blocks: number[] = []
player.onChat("printblocks", function () {
    for (let index = 0; index <= Blocks.length - 1; index++) {
        RandomBlock = Math.randomRange(0, Blocks.length - 1)
        blocks.place(blocks.blockById(Blocks[RandomBlock]), positions.create(2, 0, index))
    }
    player.say("Block removed with ID = " + Blocks.removeAt(Blocks.length - 1))
})
Blocks = [1, 2, 3, 4, 5]
```

![Remove from Array](/static/courses/csintro/arrays/act2-finished.jpg)

## Experiments

### Experiment 1 - Print Blocks and Names... Two Arrays in Parallel

```blocks
let BlockNames: string[] = []
let Blocks: number[] = []
let index = 0
player.onChat("printblocks", function () {
    for (let index2 = 0; index2 <= Blocks.length - 1; index2++) {
        blocks.place(blocks.blockById(Blocks[index2]), positions.create(2, 0, index2))
        player.say("Printing 1 " + BlockNames[index2])
    }
})
index = 0
Blocks = [159, 61, 35, 79, 56]
BlockNames = ["Terracotta", "Furnace", "Wool", "Ice", "Diamond Ore"]
```

![Two parallel arrays](/static/courses/csintro/arrays/twoparrallelarrays.png)

### Experiment 2 - Print with Data Values

```blocks
let DataValue: number[] = []
let BlockNames: string[] = []
let Blocks: number[] = []
player.onChat("PrintBlocks", function () {
    for (let index = 0; index <= Blocks.length - 1; index++) {
        if (DataValue[index] == -1) {
            blocks.place(blocks.blockById(Blocks[index]), positions.create(2, 0, index))
        } else {
            blocks.place(blocks.blockWithData(blocks.blockById(Blocks[index]), Math.randomRange(0, DataValue[index])), positions.create(2, 0, index))
        }
        player.say("Printing 1 " + BlockNames[index])
    }
})
Blocks = [251, 35, 17, 97, 5]
BlockNames = ["Concrete", "Wool", "Tree", "Stone", "Wood"]
DataValue = [15, 15, 3, 5, 5]
```

![Using Data Values to Print Blocks](/static/courses/csintro/arrays/act-exp2.jpg)