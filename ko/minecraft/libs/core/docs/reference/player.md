# 플레이어

The **player**, you, can create actions and change things about yourself with code. You can do things like make a new chat command or change your location. You can also respond to events that happen to you.

## 찾아보기

```cards
player.say("Hi!");
player.teleport(positions.create(0,0,0));
player.position();
player.name();
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

## 고급

```cards
player.execute("say Hi!");
player.tell(mobs.target(TargetSelectorKind.LocalPlayer), "Hi!");
player.onTellCommand("jump", () => {

});
player.onTeleported(() => {

});
```