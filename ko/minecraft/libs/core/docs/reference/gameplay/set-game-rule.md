# set Game Rule

Enable or disable a game rule. Game rules control what happens to players and mobs in some game situations.

```sig
gameplay.setGameRule(GameRule.PvP, false);
```

You can cause or prevent some things happening to players and mobs with `||gameplay:set rule||`. The rule is turned on by setting `true` and turned off by setting `false`.

## 매개 변수

* **rule**: the game rule to change, such as: *GameRule.PvP* > * `PvP`: players can attack each other > * `drowning damage`: staying for too long under water will damage the player > * `fall damage`: falling from really high will damage the player > * `fire damage`: fire will damage the player > * `daylight cycle`: time will advance in the game > * `mob loot`: mobs will drop loot upon dying > * `mob spawning`: mobs are able to spawn > * `weather cycle`: weather will change naturally > * `mob griefing`: mobs can affect the game world (for example, endermen picking up blocks, or creepers exploding the environment) > * `block drops`: blocks that are successfully mined will drop as an item and be collectible by players > * `keep inventory`: players will not lose their inventory upon dying
* **enabled**: set enabled: `true`, or not enabled: `false`, for the rule

## 예시

Make it always sunny in the game world by disabling daylight and weather cycles.

```blocks
gameplay.setGameRule(GameRule.DaylightCycle, false);
gameplay.setGameRule(GameRule.WeatherCycle, false);
gameplay.setWeather(Weather.Clear);
gameplay.timeSet(gameplay.time(DayTime.Day));
```