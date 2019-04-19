# Gameplay

Commands to control the game mode, weather, time and other game rules.

## Reference

```cards
gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
);
gameplay.timeSet(gameplay.time(DayTime.Day));
gameplay.timeAdd(0);
gameplay.timeQuery(TimeQuery.GameTime);
gameplay.setWeather(Weather.Clear);
gameplay.toggleDownfall();
gameplay.xp(10, mobs.target(TargetSelectorKind.LocalPlayer));
gameplay.setGameRule(GameRule.PvP, false);
gameplay.title(mobs.target(TargetSelectorKind.AllPlayers), "Title", "Sub title");
```