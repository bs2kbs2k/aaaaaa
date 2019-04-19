# Activity: How Old Are You?

## Challenges

### Challenge 1 - Compare Ages and Modify Messages

```blocks
player.onChat("age", function (num1) {
    if (num1 < 14) {
        blocks.print(
        "Youngling",
        blocks.block(Block.PinkGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    } else if (num1 == 14) {
        blocks.print(
        "Same",
        blocks.block(Block.YellowGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    } else {
        blocks.print(
        "Old Gamer",
        blocks.block(Block.BlueGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    }
})
```

![challenge 1 - modifying if then else number](/static/courses/csintro/conditionals/youngling.jpg)

![another example](/static/courses/csintro/conditionals/challenge1-result.jpg)

![some blocks just fall](/static/courses/csintro/conditionals/challenge1-result-blocks-fell.jpg)

### Challenge 2 - Compare Birthdays

```blocks
player.onChat("age", function (FriendsAge, Birthday) {
    if (FriendsAge < 14) {
        blocks.print(
        "Youngling",
        blocks.block(Block.PinkGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    } else if (FriendsAge == 14) {
        blocks.print(
        "Same",
        blocks.block(Block.YellowGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
        if (Birthday == 3) {
            blocks.print(
            "March! Me too!",
            blocks.block(Block.EmeraldBlock),
            positions.create(0, 30, 0),
            CompassDirection.West
            )
        } else {
            blocks.print(
            "Oh, mine is March!",
            blocks.block(Block.EmeraldBlock),
            positions.create(0, 30, 0),
            CompassDirection.West
            )
        }
    } else {
        blocks.print(
        "Old Gamer",
        blocks.block(Block.BlueGlazedTerracotta),
        positions.create(0, 10, 0),
        CompassDirection.West
        )
    }
})

```

![challenge 2 - modifying if then else number](/static/courses/csintro/conditionals/youngling2.jpg)

![challenge 2 - modifying if then else number](/static/courses/csintro/conditionals/same.jpg)

![challenge 2 - modifying if then else number](/static/courses/csintro/conditionals/slightlyolder.jpg)

## Experiments

## Experiment 1 - Try Other Types of Conversions

```blocks
let InputUnit = ""
let ResultUnit = ""
let Result = 0
player.onChat("weight", function (UnitofMeasureInput, Amount) {
    if (UnitofMeasureInput == 1) {
        // Convert to Pounds
        Result = Amount / 0.453592
        // For display purposes
        ResultUnit = "lbs"
        // For display purposes
        InputUnit = "kg"
    } else if (UnitofMeasureInput == 2) {
        // Convert to Kilograms
        Result = Amount * 0.453592
        // For display purposes
        ResultUnit = "kg"
        // For display purposes
        InputUnit = "lbs"
    } else {
        player.say("****MENU************MENU************MENU****")
        player.say("Convert your weight from pounds to kilograms and vice versa")
        player.say("Enter either \"1\" for pounds or \"2\" for kilograms")
        player.say("Then enter a number for your weight")
        player.say("Example command >> \"Weight 2 100\"")
        player.say("100 lbs is converted to kilograms")
        player.say("Try it out!")
        player.say("****MENU************MENU************MENU****")
    }
    if (UnitofMeasureInput != 0) {
        player.say("_______________________________________________________________")
        player.say("" + UnitofMeasureInput + (" " + InputUnit))
        player.say("is")
        player.say("" + Result + (" " + ResultUnit))
        player.say("_______________________________________________________________")
    }
})
```

## Experiment 2 - Create Blocks and Items

```blocks
player.onChat("create", function (BlockItemID) {
    if (BlockItemID < 256) {
        player.say("You chose to place a Block!")
        blocks.place(blocks.blockById(BlockItemID), positions.create(3, 3, 0))
    } else {
        player.say("You chose to equip an Item!")
        mobs.give(
        mobs.target(TargetSelectorKind.NearestPlayer),
        blocks.blockById(BlockItemID),
        1
        )
    }
    if (BlockItemID == 0) {
        player.say("  ")
        player.say("  ")
        player.say("%%%%%%%%%%  Menu  %%%%%%%%%%%%%%")
        player.say("  ")
        player.say("Type create and then a number from 0 - 452")
        player.say("Example >> \"create 36\"")
        player.say("  ")
        player.say("%%%%%%%%%%  Menu  %%%%%%%%%%%%%%")
    }
})
```