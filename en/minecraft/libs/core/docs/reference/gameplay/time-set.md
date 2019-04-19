# time Set

Set the current time to the start of day, the start of night, or to another usual of time of day.

```sig
gameplay.timeSet(DayTime.Day);
```

The point in time in the day you choose is equal to some amount of Minecraft time ticks. Minecraft uses a certain amount of ticks for each part of a day.

The `||gameplay:time set||` block an easy way to make time move to a common part of the day.

The [Minecraft wiki](http://minecraft.gamepedia.com/Day-night_cycle#24-hour_Minecraft_day) has a table to convert time of day to Minecraft ticks.

## Parameters

* **time**: the desired time of day, such as: *DayTime.Day* > * `day`: Equals 1,000 ticks (7:00 AM) > * `dawn`: Equals 0 ticks (6:00 AM) > * `midday`: Equals 6,000 ticks (12:00 PM) > * `dusk`: Equals 12,000 ticks (6:00 PM) > * `night`: Equals 13,000 ticks (7:00 PM) > * `midnight`: Equals to 18,000 ticks (12:00 AM)

## Example

Set the time to `night` (night starts at 7:00 PM or 13,000 ticks) when the player wants night.

```blocks
player.onChat("night", function () {
    gameplay.timeSet(gameplay.time(DayTime.Night))
});
```

## See Also

[`||gameplay:time add||`](/reference/gameplay/time-add)

Find out how time works in Minecraft at the [Minecraft wiki](http://minecraft.gamepedia.com/Day-night_cycle).