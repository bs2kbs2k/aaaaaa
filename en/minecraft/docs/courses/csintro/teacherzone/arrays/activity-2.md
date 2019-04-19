# Activity: Warp Belt

## Challenges

### Challenge 1 - Make Sure a Valid Jump Spot Was Entered

```blocks
let warp_array: Position[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
})
player.onChat("warp", function (Warp_LocationNum) {
    if (Warp_LocationNum <= warp_array.length) {
        player.teleport(warp_array[Warp_LocationNum - 1])
    } else {
        player.say("No such location!")
    }
})
warp_array = []

```

### Challenge 2 - Print All Saved Warp Coordinates

```blocks
let warp_array: Position[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
    ListSavedLocations()
})
player.onChat("warp", function (Warp_LocationNum) {
    if (Warp_LocationNum <= warp_array.length) {
        player.teleport(warp_array[Warp_LocationNum - 1])
    } else {
        player.say("No such location!")
    }
})
function ListSavedLocations() {
    for (let value of warp_array) {
        player.say(" " + value)
    }
}
warp_array = []

```

## Experiments

### Experiment 1 - Type any structure you might want to find in the world you are in.

```blocks
let counter = 0
let PopularLocations: string[] = []
let warp_names_array: string[] = []
let warp_array: Position[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function (SaveNameType) {
    SaveNameType += -1
    if (SaveNameType < 9 && SaveNameType > -1) {
        warp_array.push(player.position())
        warp_names_array.push(PopularLocations[SaveNameType])
        player.say("" + PopularLocations[SaveNameType] + " added...")
    } else {
        player.say("    ")
        player.say("You need to specify what kind of location you are saving!")
        player.say("Here are a list of the locations you can save")
        player.say("    ")
        player.say("1 = endcity")
        player.say("2 = fortress")
        player.say("3 = mansion")
        player.say("4 = mineshaft")
        player.say("5 = monument")
        player.say("6 = stronghold")
        player.say("7 = temple")
        player.say("8 = village")
        player.say("9 = other")
        player.say("   ")
        player.say("Example -")
        player.say("save 3")
        player.say("saves a mansion location")
        player.say("   ")
        player.say("   ")
        player.say("   ")
    }
})
player.onChat("list", function () {
    player.say("    ")
    player.say("Here is a list of all saved locations:")
    player.say("    ")
    counter = 0
    for (let value of warp_array) {
        player.say("" + warp_names_array[counter] + " : " + value)
        counter += 1
    }
    player.say("    ")
    player.say("    ")
})
player.onChat("warp", function (Warp_LocationNum) {
    if (Warp_LocationNum <= warp_array.length) {
        player.teleport(warp_array[Warp_LocationNum - 1])
    } else {
        player.say("Sorry, no such location")
    }
})
warp_names_array = []
warp_array = []
PopularLocations = ["endcity", "fortress", "mansion", "mineshaft", "monument", "stronghold", "temple", "village", "other"]

```