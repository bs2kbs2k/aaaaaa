# time Query

Get the current time of day, in game ticks.

```sig
gameplay.timeQuery(TimeQuery.GameTime);
```

The [Minecraft wiki](http://minecraft.gamepedia.com/Day-night_cycle#24-hour_Minecraft_day) has a table to convert time of day to Minecraft ticks.

## 매개 변수

* **query**: the type of time to query > * `gametime`: the number of game ticks since the creation of the world > * `daytime`: the current time of day in the game > * `day`: the number of game days since the creation of the world > * `real life`: the real time of day, in game ticks

## 예시

Set the time of day in the game to the same time as real life.

```blocks
gameplay.timeSet(gameplay.timeQuery(TimeQuery.RealLife));
```

## 참고 항목

[`||gameplay:time set||`](/reference/gameplay/time-set)