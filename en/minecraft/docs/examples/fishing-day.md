# Fishing Day

![Fishing in the sea](/static/mods/fishing.jpg)

Such a nice morning to go fishing! Grab your boat and fishing rod, and head out to sea! Don't forget your apples in case you get sick...

## Try the code:

```blocks
player.onItemInteracted(Item.Boat, function () {
    gameplay.setWeather(Weather.Clear)
    gameplay.timeSet(gameplay.time(DayTime.Dawn))
})
player.onTravelled(TravelMethod.Riding, function () {
    mobs.applyEffect(Effect.Nausea, mobs.target(TargetSelectorKind.LocalPlayer), 10, 1)
})
player.onItemInteracted(Item.FishingRod, function () {
    mobs.spawn(AnimalMob.Dolphin, positions.create(2, 4, 0))
    mobs.spawn(AnimalMob.Pufferfish, positions.create(-2, 4, 0))
    mobs.spawn(AnimalMob.Salmon, positions.create(0, 4, 2))
    mobs.spawn(AnimalMob.TropicalFish, positions.create(0, 4, -2))
    mobs.spawn(AnimalMob.Cod, positions.create(2, 4, 2))
    mobs.spawn(AnimalMob.Squid, positions.create(-2, 4, -2))
})
player.onItemInteracted(Item.Apple, function () {
    mobs.clearEffect(mobs.target(TargetSelectorKind.LocalPlayer))
})
player.say("Lets go fishing!")
player.say("Get a boat and a fishing rod")
```