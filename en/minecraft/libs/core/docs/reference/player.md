# Player

The **player**, you, can create actions and change things about yourself with code. You can do things like make a new chat command or change your location. You can also respond to events that happen to you.

## Reference

```cards
player.say("Hi!");
player.teleport(positions.create(0,0,0));
player.position();
player.name();
player.onItemInteracted(Item.IronShovel, function () {

})
player.onChat("jump", function () {

});
player.runChatCommand("jump");
player.runChatCommandWithArguments("jump", "10");
player.onDied(() => {

});
player.onTravelled(TravelMethod.Walk, () => {

});
player.onArrowShot(() => {

});
```

## Advanced

```cards
player.execute("say Hi!");
player.tell(mobs.target(TargetSelectorKind.LocalPlayer), "Hi!");
player.onTellCommand("jump", () => {

});
player.onTeleported(() => {

});
```