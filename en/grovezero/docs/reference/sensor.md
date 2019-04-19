# Sensor

```cards
sensor.onIMU(IMUEvent.FreeFall, function () { })
sensor.onLight(LightEvent.Light, function () { })
sensor.onLoudSound(function() { })
sensor.onTemperature(TemperatureEvent.Cold, function () { })
sensor.acceleration(Axis.X)
sensor.lightLevel()
sensor.soundLevel()
sensor.temperature()
sensor.wasIMUTriggered(IMUEvent.FreeFall)
sensor.wasLightTriggered(LightEvent.Light)
sensor.wasLoudSoundTriggered()
sensor.wasTemperatureTriggered(TemperatureEvent.Cold)
sensor.setLightThreshold(LightEvent.Dark, 0)
sensor.setSoundThreshold(0)
sensor.setTemperatureThreshold(TemperatureEvent.Cold, 0)
```

## See also

[acceleration](/reference/sensor/acceleration), [light level](/reference/sensor/light-level), [sound level](/reference/sensor/sound-level), [temperature](/reference/sensor/temperature), [was imu triggered](/reference/sensor/was-imu-triggered), [was light triggered](/reference/sensor/was-light-triggered), [was loud sound triggered](/reference/sensor/was-loud-sound-triggered), [was temperature triggered](/reference/sensor/was-temperature-triggered), [on imu](/reference/sensor/on-imu), [on light](/reference/sensor/on-light), [on loud sound](/reference/sensor/on-loud-sound), [on temperature](/reference/sensor/on-temperature), [set light threshold](/reference/sensor/set-light-threshold), [set sound threshold](/reference/sensor/set-sound-threshold), [set temperature threshold](/reference/sensor/set-temperature-threshold)