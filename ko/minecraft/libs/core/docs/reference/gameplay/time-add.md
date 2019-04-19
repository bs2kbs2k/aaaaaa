# time Add

Add ticks to the current time of day.

```sig
gameplay.timeAdd(100);
```

You move time forward by adding time ticks to the current time.

## 매개 변수

* **amount**: the number of ticks added to the current time of day, like: `100` ticks

The [Minecraft wiki](http://minecraft.gamepedia.com/Day-night_cycle#24-hour_Minecraft_day) has a table to convert time of day to Minecraft ticks.

## 예시

Adds ticks to the game time as you walk around. It's time travel!

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    gameplay.timeAdd(300)
});
```

## 참고 항목

[`||gameplay:time set||`](/reference/gameplay/time-set)

Find out how time works in Minecraft at the [Minecraft wiki](http://minecraft.gamepedia.com/Day-night_cycle).